# Image Retrieval

## 图像检索



课题组有个服装检索的国基，组里有好几个搞相关的研究，每次报告都会有他们读过的论文，我耳濡目染，也算是半个检索人了。之前是李菲菲她们的BOW词包模型，后来又到了deep learning大放异彩。不过就我的感觉来看，目前并没有什么特别有效的方法，实验的数据量也不大，且基本都是闭源的，无从验证算法的优劣，这点和tracking是有很大区别的。排序是google的PR算法，我看到好多算法都有借鉴它。

**综述数据集**

[各大搜索引擎的比较 - Tuesday - 博客频道 - CSDN.NET](http://blog.csdn.net/naturebe/article/details/7910423)

[基于内容图像检索的若干技术研究 - William Valentine - 博客频道 - CSDN.NET](http://blog.csdn.net/williamvalentine/article/details/6534198)

[Image Retrieval: Ideas, influences, and trends of the new age 图像检索综述 文献翻译(一) - William Valentine - 博客频道 - CSDN.NET](http://blog.csdn.net/williamvalentine/article/details/5886804)

[Image Retrieval: Ideas, Influences, and Trends of the New Age - zjgtan - 博客园](http://www.cnblogs.com/zjgtan/archive/2013/04/07/3006357.html)

[互联网环境下大规模图像的内容分析笔记 - zjgtan - 博客园](http://www.cnblogs.com/zjgtan/archive/2013/04/11/3014682.html)

**爬虫**

[一个简单的多线程爬虫 - CodeMeals - 博客园](http://www.cnblogs.com/fengfenggirl/p/3737738.html)

**PageRank**

[搜索引擎基本原理 - Keosu - 博客园](http://www.cnblogs.com/answeryi/archive/2012/09/30/2709291.html)

[Google 的秘密- PageRank 彻底解说 中文版](http://www.kreny.com/pagerank_cn.htm)

[PageRank算法 - guisu，程序人生。 逆水行舟，不进则退。 - 博客频道 - CSDN.NET](http://blog.csdn.net/hguisu/article/details/7996185)

[深入探讨PageRank（一）：PageRank算法原理入门 - 愤怒的小狐狸----博客专栏 - 博客频道 - CSDN.NET](http://blog.csdn.net/monkey_d_meng/article/details/6554518)

[谷歌背后的数学](http://www.changhai.org/articles/technology/misc/google_math.php)

[数据挖掘10大算法(1)——PageRank - 风中之炎 - 博客园](http://www.cnblogs.com/FengYan/archive/2011/11/12/2246461.html)

[搜索引擎技术之概要预览 - 结构之法 算法之道 - 博客频道 - CSDN.NET](http://blog.csdn.net/v_july_v/article/details/6827391)

[PageRank实践-博客园用户PageRank排名 - CodeMeals - 博客园](http://www.cnblogs.com/fengfenggirl/p/pagerank-cnblogs.html)

[利用python、Gephi绘制人人的社交网络图 - Code my world - 博客频道 - CSDN.NET](http://blog.csdn.net/zdw12242/article/details/8687644)

[二十大数据可视化工具点评 - IT经理网](http://www.ctocio.com/hotnews/8874.html)

[PageRank算法简介及Map-Reduce实现 - CodeMeals - 博客园](http://www.cnblogs.com/fengfenggirl/p/pagerank-introduction.html)

**LSH**

[局部敏感哈希(Locality-Sensitive Hashing, LSH)方法介绍 - CVPR|OpenCV|图像检索|视频检索 - 博客频道 - CSDN.NET](http://blog.csdn.net/icvpr/article/details/12342159)

[Locality Sensitive Hashing (LSH) Home Page](http://www.mit.edu/%7Eandoni/LSH/)

[实习日记：图像检索算法 LSH 的总结与分析 - 进阶之路 - 博客园](http://www.cnblogs.com/liyangguang1988/p/3875998.html)

[Hamming Embedding 汉明嵌入简介 - defineWL的专栏 - 博客频道 - CSDN.NET](http://blog.csdn.net/definewl/article/details/41217441)

[CVPR14与图像视频检索相关的论文 - 姜文晖的博客 - 博客频道 - CSDN.NET](http://blog.csdn.net/jwh_bupt/article/details/23039357)

[百度图像搜索探秘_dengyafeng_新浪博客](http://blog.sina.com.cn/s/blog_6ae183910101gily.html)

[Computer Vision Group - Shape Analysis](http://vision.in.tum.de/research/shape_analysis)

[SCHEMA - Network of Excellence in Content-Based Semantic Scene Analysis and Information Retrieval](http://www.iti.gr/SCHEMA/index.html)

[Gunhee Kim @ CSD.CMU.EDU](http://www.cs.cmu.edu/%7Egunhee/index.html#pub_vis)

[www.liangzheng.com.cn/Project/project_baseline.html](http://www.liangzheng.com.cn/Project/project_baseline.html)

[Holidays dataset](http://lear.inrialpes.fr/people/jegou/data.php#holidays)

[Bag of Word闲谈_zjjconan_新浪博客](http://blog.sina.com.cn/s/blog_4cb0b54301014hxu.html)

[用python做网页抓取与解析入门笔记 - chentingpc - Ting Chen](http://chentingpc.me/article/article.php?id=961)

[图像检索：一维直方图+EMD距离 - wxcdzhangping的专栏 - 博客频道 - CSDN.NET](http://blog.csdn.net/zhangping1987/article/details/37560397)

[竞赛描述 ](http://www.pkbigdata.com/c/00000000057)

[2012年06月03日_清醒网_新浪博客](http://blog.sina.com.cn/s/blog_6728688a01016yz2.html)

[从搜老婆到看AV，拍照搜索未来八大匪夷所思用法_互联网的一些事](http://www.yixieshi.com/it/18682.html)

[拍照搜索巅峰对决：手机百度完胜谷歌Goggles_DoNews-IT数码](http://www.donews.com/it/201408/2834827.shtm)

[用Python和OpenCV创建一个图片搜索引擎的完整指南 - Python - 伯乐在线](http://python.jobbole.com/80860/)

[Private Content Based Image Retrieval](http://cvit.iiit.ac.in/projects/cbir/PCBIR/index.html)

[Submodular Reranking with Multiple Feature Modalities for Image Retrieval](http://www.umiacs.umd.edu/%7Efyang/papers/submodular.html)

**LTR**

[史上最全的搜索下拉提示用户交互研究——读《An Eye-tracking Study of User Interactions with Query Auto Completion》 - Stay hungry, Stay foolish - 博客频道 - CSDN.NET](http://blog.csdn.net/huagong_adu/article/details/40951409)

[学习排序 Learning to Rank 小结 - nanjunxiao的专栏 - 博客频道 - CSDN.NET](http://blog.csdn.net/nanjunxiao/article/details/8976195)

[浅谈网络广告 - Stay hungry, Stay foolish - 博客频道 - CSDN.NET](http://blog.csdn.net/huagong_adu/article/details/7270578)