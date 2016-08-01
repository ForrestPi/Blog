---
layout: post
title: thread pool
category: project
description: 线程池
---
##半同步半异步线程池##
半同步半异步模式线程池：多线程处理更灵活性


###线程池有两个活动过程：###
> + 外面不停的往线程池添加任务
> + 线程池内部不停的取任务执行

引入设计模式思想，实现解耦，提高代码可复用性
生产者-消费者模式
> +  同步层是生产者，不断将新任务丢到排队层
> +  消费者是异步层，线程执行排队层的任务
>   ![threadpool](/Code/images/threadpool/threadpool.png)

###半同步半异步线程池-消费者###

![consumer](/Code/threadpool/consumer.png)

###半同步半异步线程池-生产者###

![producer](/Code/images/threadpool/producer.png)

###半同步半异步线程池特性###
半同步半异步线程池特性介绍：
> +  锁机制、条件变量实现线程安全
> +  右值引用、move移动语义、forward完美转发减少内存占用率
> +  实现对不同系统平台以及不同编译环境的兼容性
> +  半同步半异步线程池为轻量级线程池库，具有极佳的可伸缩性
> +  开源、通用性强

###源码链接###
> [线程池库](https://github.com/ForrestPi/Cplusplus11_project/tree/master/threadPool"ThreadPool")。




[ForrestPi]: http://forrestpi.github.io/	"ForrestPi"
[1]:    {{ page.url}}  ({{ page.title }})