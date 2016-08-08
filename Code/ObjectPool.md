# ObjectPool

##                                                        一个超级对象池的实现



对象池对于创建开销比较大的对象来说很有意义，为了避免重复创建开销比较大的对象，我们可以通过对象池来优化。对象池的思路比较简单，事先创建好一批对
象，放到一个集合中，以后每当程序需要新的对象时候，都从对象池里获取，每当程序用完该对象后，都把该对象归还给对象池。这样会避免重复的对象创建，提高
程序性能。先来看看对象池的简单实现：

```c++
#include <list>
 
template<typename Object>
class ObjectPool
{
public:
 
    ObjectPool(size_t unSize) :
        m_unSize(unSize)
    {
        for (size_t unIdx = 0; unIdx < m_unSize; ++ unIdx)
    {
        m_oPool.push_back(new Object());
    }
    }
 
    ~ObjectPool()
    {
    typename std::list<Object *>::iterator oIt = m_oPool.begin();
    while (oIt != m_oPool.end())
    {
        delete (*oIt);
        ++ oIt;
    }
    m_unSize = 0;
    }
 
    Object * GetObject()
    {
        Object * pObj = NULL;
        if (0 == m_unSize)
        {
            pObj = new Object();
        }
        else
        {
            pObj = m_oPool.front();
            m_oPool.pop_front();
            -- m_unSize;
        }
 
        return pObj;
    }
 
    void ReturnObject(Object * pObj)
    {
        m_oPool.push_back(pObj);
        ++ m_unSize;
    }
 
private:
    size_t m_unSize;
    std::list<object *> m_oPool;
};
```

这个object pool的实现很典型，初始创建一定数量的对象，取的时候就直接从池子中取，用完之后再回收到池子。一般的对象池的实现思路和这个类似，这种实现方式虽然能达到目的，但是存在以下不足：

1. 对象池ObjectPool<T>只能容纳特定类型的对象，不能容纳所有类型的对象，可以支持重载的和参数不同的构造函数；
2. 对象用完之后需要手动回收，用起来不够方便，更大的问题是存在忘记回收的风险；

　　我希望能有一个更强大的对象池，这个对象池能容纳所有的对象，还能自动回收用完了对象，不需要手动回收，用起来更方便。要实现这样的对象池需要解决前面提到的两个问题，通过c++11就可以解决这两个问题。

　　对于问题1：容纳所有的对象。本质上需要将对象池中的对象类型擦除，这里用Any类型就可以解决。

　　对于问题2：自动回收用完的对象。这里用智能指针就可以解决，在创建智能指针时可以指定删除器，在删除器中不删除对象，而是回收到对象池中，而这个过程对外界来说是看不见的，由智能指针自己完成。

```c++
#include <string>
#include <functional>
#include <tuple>
#include <map>

#include "Any.hpp"

const int MaxObjectNum = 10;

class ObjectPool
{
    template<typename T, typename... Args>
    using Constructor = std::function<std::shared_ptr<T>(Args...)>;
public:

    ObjectPool() : needClear(false)
    {
    }

    ~ObjectPool()
    {
        needClear = true;
    }

    //默认创建多少个对象
    template<typename T, typename... Args>
    void Create(int num)
    {
        if (num <= 0 || num > MaxObjectNum)
            throw std::logic_error("object num errer");

        auto constructName = typeid(Constructor<T, Args...>).name();

        Constructor<T, Args...> f = [constructName, this](Args... args)
        {
            return createPtr<T>(string(constructName), args...);
        };

        m_map.emplace(typeid(T).name(), f);

        m_counter.emplace(constructName, num);
    }

    template<typename T, typename... Args>
    std::shared_ptr<T> createPtr(std::string& constructName, Args... args)
    {
        return std::shared_ptr<T>(new T(args...), [constructName, this](T* t)
        {
            if (needClear)
                delete[] t;
            else
                m_object_map.emplace(constructName, std::shared_ptr<T>(t));
        });
    }

    template<typename T, typename... Args>
    std::shared_ptr<T> Get(Args... args)
    {
        using ConstructType = Constructor<T, Args...>;

        std::string constructName = typeid(ConstructType).name();
        auto range = m_map.equal_range(typeid(T).name());

        for (auto it = range.first; it != range.second; ++it)
        {
            if (it->second.Is<ConstructType>())
            {
                auto ptr = GetInstance<T>(constructName, args...);

                if (ptr != nullptr)
                    return ptr;

                return CreateInstance<T, Args...>(it->second, constructName, args...);
            }
        }

        return nullptr;
    }

private:
    template<typename T, typename... Args>
    std::shared_ptr<T> CreateInstance(Any& any,
        std::string& constructName, Args... args)
    {
        using ConstructType = Constructor<T, Args...>;
        ConstructType f = any.AnyCast<ConstructType>();

        return createPtr<T, Args...>(constructName, args...);
    }

    template<typename T, typename... Args>
    void InitPool(T& f, std::string& constructName, Args... args)
    {
        int num = m_counter[constructName];

        if (num != 0)
        {
            for (int i = 0; i < num - 1; i++)
            {
                m_object_map.emplace(constructName, f(args...));
            }
            m_counter[constructName] = 0;
        }
    }

    template<typename T, typename... Args>
    std::shared_ptr<T> GetInstance(std::string& constructName, Args... args)
    {
        auto it = m_object_map.find(constructName);
        if (it == m_object_map.end())
            return nullptr;

        auto ptr = it->second.AnyCast<std::shared_ptr<T>>();
        if (sizeof...(Args)>0)
            *ptr.get() = std::move(T(args...));

        m_object_map.erase(it);
        return ptr;
    }

private:
    std::multimap<std::string, Any> m_map;
    std::multimap<std::string, Any> m_object_map;
    std::map<std::string, int> m_counter;
    bool needClear;
};
```