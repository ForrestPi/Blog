# Resources in Visual Tracking V2.0

## 视觉追踪资源



**这是我发表在valseonline上的技术报告，系统总结了单目标 model-tracking当前的现状。**

**Tracking是计算机视觉非常活跃的研究领域，每年在CVPR、ICCV、ECCV和PAMI等国际会议和期刊上都有大量相关的文章发表。它的分类有很多，根据追踪目标数量的不同，可分为单目标追踪和多目标追踪，根据是否在线更新模板可分为离线追踪和在线追踪。早期的研究多关注于离线追踪，代表性方法有Kalman滤波和粒子滤波，甚至meanshift在大行其道时也曾登上PAMI的大堂。不过由于近年来tracking发展很快，这些方法都已经濒临淘汰，对他们的总结见下面列出的Tutorials-Advances inVisual Tracking，由于精力有限，本文只关注在线单目标追踪方法。多目标追踪见ReferenceGuide: Multiple Object Tracking、Multi-Object Tracking和Multi_Object TrackingFramework，他们总结的很好，我就不班门弄斧了。

上次在[CSDN发布的](http://blog.csdn.net/minstyrain/article/details/38640541)只是单纯的连接，并不能节省大家宝贵的时间，这次相比来说就要全面的多。提醒大家一句CDSN上基本都是初学者的总结，断章取义、望文生义等屡见不鲜，还是自己真读过才会领会作者的真实意图。先来几篇我认为比较写好的吧：

**视频讲座**

VALSE曾做过几期有关tracking的讲座，包括专题[tracking](http://valse.mmcheng.net/tracking/)，张开华老师的[FCT](http://valse.mmcheng.net/%E5%A5%BD%E6%96%87%E4%BD%9C%E8%80%85%E9%9D%A2%E6%8E%88%E6%8B%9B-20150128/)，[贾奎ROML](http://valse.mmcheng.net/%E5%A5%BD%E6%96%87%E4%BD%9C%E8%80%85%E9%9D%A2%E6%8E%88%E6%8B%9B-20150506/)，视频下载链接[http://vision.ouc.edu.cn/valse/](http://vision.ouc.edu.cn/valse/)。Techtalks上录制的CVPR tracking相关的视频：CVPR2014：[AdaptiveColor Attributes for Real-Time Visual Tracking](http://techtalks.tv/talks/adaptive-color-attributes-for-real-time-visual-tracking-2/60282/)CVPR2012：[RobustVisual Tracking via Multi-Task Sparse Learning](http://techtalks.tv/talks/robust-visual-tracking-via-multi-task-sparse-learning/56242/)其他的我相信搞计算机的应该有相应的搜索能力了。

**值得看的中文博客**        

 首推[Correlation Filter in Visual Tracking](http://www.cnblogs.com/hanhuili/)，它给出了算法的直觉，逻辑推理的过程值得深究。       [目标跟踪学习系列](http://blog.csdn.net/ikerpeng/article/details/20703421)共13篇，基本总结了online-tracker所有要看的东西。

**各大牛人的主页**

一定要经常看，不时就会有新的东西：[Ming-Hsuan Yang's HomePage](http://faculty.ucmerced.edu/mhyang/)[KyoungMuLee](http://cv.snu.ac.kr/jhkwon/tracking/)[Arnold Smeulders](http://staff.science.uva.nl/%7Esmeulder/)[Haibin Ling](http://www.dabi.temple.edu/%7Ehbling/publication-selected.htm)[Lei Zhang](http://www4.comp.polyu.edu.hk/%7Ecslzhang/papers.htm)[Horst Possegger](http://lrs.icg.tugraz.at/members/possegger#occgeo)[Sinisa Todorovic](http://web.engr.oregonstate.edu/%7Esinisa/)[Dr. Zdenek Kalal](http://personal.ee.surrey.ac.uk/Personal/Z.Kalal/)[Charles Bibby | ResearchInterest: Active Vision and SLAM](http://www.robots.ox.ac.uk/%7Ecbibby/research_pwp.shtml)[Kevin Cannons, Mitacs Elevate PostdoctoralFellow](http://www.cse.yorku.ca/%7Ekcannons/)[卢湖川](http://ice.dlut.edu.cn/lu/publications.html)[João F. Henriques](http://home.isr.uc.pt/%7Ehenriques/index.html)[Shai Avidan](http://www.eng.tau.ac.il/%7Eavidan/)[www.eng.tau.ac.il/~oron/](http://www.eng.tau.ac.il/%7Eoron/)[Helmut Grabner](http://www.vision.ee.ethz.ch/%7Ehegrabne/)[Anton Milan](http://www.milanton.de/)[Tomáš Vojíř](http://cmp.felk.cvut.cz/%7Evojirtom/)[Naiyan Wang - Home](http://winsty.net/index.html)[西北大学吴郢](http://users.eecs.northwestern.edu/%7Eyingwu/)[信息与控制学院--吴 毅](http://web2.nuist.edu.cn:8080/xky/2013-11/2013112141929.html)[张开华](http://web2.nuist.edu.cn/jszy/Professor.aspx?id=1991)[Sam Hare](http://www.samhare.net/)[Bohyung Han's homepage](http://cvlab.postech.ac.kr/%7Ebhhan/)[vision.cse.psu.edu/home/home.shtml](http://vision.cse.psu.edu/home/home.shtml)[张天柱](https://sites.google.com/site/zhangtianzhu2012/)[Welcome to Jianming Zhang's Home Page](http://cs-people.bu.edu/jmzhang/)[Charles Bibby | ResearchInterest: Active Vision and SLAM](http://www.robots.ox.ac.uk/%7Ecbibby/index.shtml)[Deva Ramanan - UC Irvine - Computer Vision](http://www.ics.uci.edu/%7Edramanan/)[Georg Nebehay](http://www.gnebehay.com/publications/)[文珑银](http://www.cbsr.ia.ac.cn/users/lywen/)帖子长度有限制，不过这难不倒技术宅，我把文档的pdf版本放在了[github](https://github.com/imistyrain/OpenTracking)上，也欢迎大家补充相关资料。

一、Survey and benchmark：

1. [VOT challenge](http://www.votchallenge.net/)，这个不用说了吧，大名鼎鼎，如雷贯耳，如果连这个都不知道，基本上不用在tracking圈混了。
2. PAMI2014：[Visual Tracking_ An Experimental Survey](http://74.125.12.3/search?newwindow=1&q=Visual+Tracking_+An+Experimental+Survey&oq=Visual+Tracking_+An+Experimental+Survey&gs_l=serp.12..0i13l2.68555.68555.0.69234.1.1.0.0.0.0.475.475.4-1.1.0....0...1c.1.51.serp..0.1.473.jnnqc1LhZOk)，阿姆斯特丹大学建立的包括300多个视频序列的库，代码：[http://alov300pp.joomlafree.it/trackers-resource.html](http://alov300pp.joomlafree.it/trackers-resource.html)
3. CVPR2013:[Online Object Tracking: A Benchmark](http://visual-tracking.net/)(需翻墙) ，吴毅老师的库，刚开始是50个序列，后扩展到100个，为评估初始化对tracker的影响，加入了OPE、TRE、SRE和TRER、SRER等评估指标。
4. ICCV2013:Finding the Best from the Second Bests – Inhibiting Subjective Bias inEvaluation of Visual Tracking Algorithms
5. Signal Processing 2011：[Video Tracking Theory and Practice](http://download.csdn.net/detail/mgqmha/4450053)
6. ACCV2006：[Tutorials-Advances in Visual Tracking](http://www.accv2010.org/tut_tracking.html)：中文：[视觉跟踪的进展](http://www.tuicool.com/articles/e2q6nm)
7. Evaluation of an online learning approach for robust object tracking

 

二、研究团体：

1. University of California at Merced：[Ming-Hsuan Yang](http://faculty.ucmerced.edu/mhyang/)视觉跟踪当之无愧第一人，后面的人基本上都和气其有合作关系，他引近9000

[Publications](http://faculty.ucmerced.edu/mhyang/pubs.html)PAMI：6，CVPR：26，ECCV：17，BMCV：6，NIPS：6，IJCV：3，ACCV：3

代表作：Robust Visual Tracking via Consistent Low-Rank Sparse Learning

**FCT**,IJCV2014:Fast Compressive Tracking

**RST**,PAMI2014:Robust Superpixel Tracking; SPT,ICCV2011, Superpixel tracking

**SVD**,TIP2014:Learning Structured Visual Dictionary for Object Tracking

ECCV2014: Spatiotemporal Background Subtraction Using Minimum Spanning Tree and Optical Flow

PAMI2011:Robust Object Tracking with Online Multiple Instance Learning

**MIT**,CVPR2009: Visual tracking with online multiple instance learning

IJCV2008: Incremental Learning for Robust Visual Tracking

 

1. Seoul National University Professor：[KyoungMuLee](http://cv.snu.ac.kr/jhkwon/tracking/)2013年在PAMI上发表5篇，至今无人能及

[文献列表](http://cv.snu.ac.kr/international)PAMI:13,CVPR:30,ECCV:12,ICCV:8,PR:4

PAMI2014：A Geometric Particle Filter for Template-Based Visual Tracking

ECCV2014: Robust Visual Tracking with Double Bounding Box Model

PAMI2013:Highly Nonrigid Object Tracking via Patch-based Dynamic Appearance Modeling

CVPR2014: Interval Tracker: Tracking by Interval Analysis

CVPR2013: Minimum Uncertainty Gap for Robust Visual Tracking

CVPR2012:Robust Visual Tracking using Autoregressive Hidden Markov Model

**VTS** ,ICCV2011:Tracking by Sampling Trackers.

**VTD**,CVPR2010: Visual Tracking Decomposition

**TST**,ICCV2011: Tracking by sampling trackers

1. Temple University，[凌海滨](http://www.dabi.temple.edu/%7Ehbling/)

[Publication List](http://www.dabi.temple.edu/%7Ehbling/publication-selected.htm) PMAI:4,CVPR:19,ICCV:17,ECCV:5,TIP:9

CVPR2014:Multi-target Tracking with Motion Context in Tenor Power Iteration

ECCV2014:Transfer Learning Based Visual Tracking with Gaussian Process Regression

ICCV2013:Finding the Best from the Second Bests - Inhibiting Subjective Bias in Evaluation of Visual Tracking Algorithms

CVPR2013: Multi-target Tracking by Rank-1 Tensor Approximation

CVPR2012:Real Time Robust L1 Tracker Using Accelerated Proximal Gradient Approach

TIP2012: Real-time Probabilistic Covariance Tracking with Efficient Model Update

ICCV2011: Blurred Target Tracking by Blur-driven Tracker

PAMI2011ICCV2009: Robust Visual Tracking and Vehicle Classification via Sparse Representation

ICCV2011:Robust Visual Tracking using L1 Minimization

**L1O**,CVPR2011: Minimum error bounded efficient l1 tracker with occlusion detection

**L1T**, ICCV2009:Robust visual tracking using l1 minimization

1. Hong Kong Polytechnic University Associate Professor: [Lei Zhang](http://www4.comp.polyu.edu.hk/%7Ecslzhang/)

[Papers](http://www4.comp.polyu.edu.hk/%7Ecslzhang/papers.htm)PAMI:2,CVPR:18,ICCV:14,ECCV:12,ICPR:6,PR:28,TIP:4

**STC**,ECCV2014: Fast Tracking via Dense Spatio-Temporal Context Learning

**FCT**,PAMI2014,ECCV2012:[Fast Compressive Tracking](http://www4.comp.polyu.edu.hk/%7Ecslzhang/CT/CT.htm), Minghsuan Yang

IET Computer Vision2012:Scale and Orientation Adaptive Mean Shift Tracking

IJPRAI2009:Robust Object Tracking using Joint Color-Texture Histogram

1. 大连理工大学教授 [卢湖川](http://ice.dlut.edu.cn/lu/publications.html)国内追踪领域第一人

CVPR2014:Visual Tracking via Probability Continuous Outlier Model

TIP2014:Visual Tracking via Discriminative Sparse Similarity Map

TIP2014: Robust Superpixel Tracking

TIP2014: Robust Object Tracking via Sparse Collaborative Appearance Model

CVPR2013: Least Soft-threshold Squares Tracking, Minghsuan Yang

TIP2013:[Online Object Tracking with Sparse Prototypes](http://ice.dlut.edu.cn/lu/Project/TIP12-SP/TIP12-SP.htm), Minghsuan Yang

Signal Processing Letters2013: Graph-Regularized Saliency Detection With Convex-Hull-Based Center Prior

Signal Processing2013: On-line Learning Parts-based Representation via Incremental Orthogonal Projective Non-negative Matrix Factorization

CVPR2012:[Robust Object Tracking viaSparsity-based Collaborative Model](http://ice.dlut.edu.cn/lu/Project/cvpr12_scm/cvpr12_scm.htm), Minghsuan Yang

CVPR2012:[Visual Tracking via Adaptive Structural Local Sparse Appearance Model](http://ice.dlut.edu.cn/lu/Project/cvpr12_jia_project/cvpr12_jia_project.htm), Minghsuan Yang

Signal Processing Letters 2012:Object tracking via 2DPCA and L1-regularization

IET Image Processing 2012:Visual Tracking via Bag of Features

ICPR2012: Superpixel Level Object Recognition Under Local Learning Framework

ICPR2012: Fragment-Based Tracking Using Online Multiple Kernel Learning

ICPR2012: Object Tracking Based On Local Learning

ICPR2012: Object Tracking with L2_RLS

ICPR2011:Complementary Visual Tracking

FG2011:Online Multiple Support Instance Tracking

Signal Processing2010: A novel method for gaze tracking by local pattern model and support vector regressor

ACCV2010: On Feature Combination and Multiple Kernel Learning for Object Tracking

ACCV: Robust Tracking Based on Pixel-wise Spatial Pyramid and Biased Fusion

ACCV2010: Human Tracking by Multiple Kernel Boosting with Locality Affinity Constraints

ICCV2011:Superpixel Tracking, Minghsuan Yang

ICPR2010: Robust Tracking Based on Boosted Color Soft Segmentation and ICA-R

ICPR2010: Incremental MPCA for Color Object Tracking

ICPR2010: Bag of Features Tracking

ICPR2008: Gaze Tracking By Binocular Vision and LBP Features

1. 南京信息工程大学教授,[KaiHua Zhang](http://smart.nuist.edu.cn/People/khzhang/khzhang.html)

**FCT**,PAMI2014:Fast Compressive Tracking, L. Zhang, and M-H. Yang

Trans. Circuits and Systems for Video Technology2013:Robust Object Tracking via Active Feature Selection, L. Zhang, M-H. Yang

TIP2013:Real-Time Object Tracking via Online Discriminative Feature Selection, L. Zhang, and M-H. Yang

1. Oregonstate Professor,[Sinisa Todorovic](http://web.engr.oregonstate.edu/%7Esinisa/)由视频分割转向Tracking

**CSL**,CVPR2014: Multi-Object Tracking via Constrained Sequential Labeling

CVPR2011:Multiobject Tracking as Maximum Weight Independent Set

1. Graz University of Technology, Austria，[Horst Possegger](http://lrs.icg.tugraz.at/members/possegger#occgeo)博士

CVPR2014:Occlusion Geodesics for Online Multi-Object Tracking

CVPR2013: Robust Real-Time Tracking of Multiple Objects by Volumetric Mass Densities

1. 马里兰大学[Zdenek Kalal](http://personal.ee.surrey.ac.uk/Personal/Z.Kalal/)博士

**TLD**,PAMI2011: Tracking-Learning-Detection

TIP2010: Face-TLD: Tracking-Learning-Detection Applied to Faces

ICPR2010:Forward-Backward Error: Automatic Detection of Tracking Failures

CVPR2010: P-N Learning: Bootstrapping Binary Classifiers by Structural Constraints

BMVC2008: Weighted Sampling for Large-Scale Boosting

中文讲解：

[TLD视觉跟踪算法](http://blog.sina.com.cn/s/blog_6163bdeb0102eh7b.html)

[TLD源码深度分析](http://quandb2007.blog.163.com/blog/static/41878875201351241741534/)

[庖丁解牛TLD](http://blog.sina.com.cn/s/blog_73ee929c01010yok.html)

[TLD（Tracking-Learning-Detection）学习与源码理解](http://blog.csdn.net/zouxy09/article/details/7893011)

 

三、其他早期工作：

[Tracking of a Non-Rigid Objectvia Patch-based Dynamic Appearance Modeling and Adaptive Basin Hopping Monte Carlo Sampling](http://cv.snu.ac.kr/research/%7Ebhmctracker/)

[tracking-by-detection](http://www.vision.ee.ethz.ch/showroom/tracking/)

[粒子滤波 演示与opencv代码](http://blog.csdn.net/onezeros/article/details/6319180)

[opencv学习笔记-入门（6）-camshift](http://blog.csdn.net/wobuaishangdiao/article/details/7660668)

[Camshift算法原理及其Opencv实现](http://blog.csdn.net/leixiaohua1020/article/details/12236091)

[Camshift算法](http://blog.csdn.net/seawaywjd/article/details/7458196) 

[CamShift算法，OpenCV实现1--Back Projection](http://blog.csdn.net/houdy/article/details/175739)

[**目标跟踪学习笔记****_2(particle filter****初探****1)**](http://www.cnblogs.com/tornadomeet/archive/2012/03/18/2404817.html)

[**目标跟踪学习笔记****_3(particle filter****初探****2)**](http://www.cnblogs.com/tornadomeet/archive/2012/05/08/2490943.html)

[**目标跟踪学习笔记****_4(particle filter****初探****3)**](http://www.cnblogs.com/tornadomeet/archive/2012/06/23/2559193.html)

[目标跟踪学习系列一:on-line boosting and vision 阅读](http://blog.csdn.net/ikerpeng/article/details/18985573)