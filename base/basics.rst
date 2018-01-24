.. _basics:

入门基础
=====================================================================


编程语言: Python
--------------------------------------
Python入门相对容易又可以干很多事(网站,运维,数据,爬虫等），是一门方便的工具语言。2016年TIOBE排名显示Python已经名列第四，成为脚本语言之首。
国外的Youtube，Instagram，Pinterest，Reddit，Dropbox，Disqus，
Quora等知名应用一开始都是基于Python构建，国内的豆瓣，知乎，果壳，饿了么，搜狐等也是Python应用的典型。这也给了国内Python开发者一阵强心剂，Python的生态环境可以支撑起重量级的
产品。这里不想挑起语言之争，php，nodejs，java，ruby等都有丰富的生态环境。不过目前来看，技术选型用Python在招聘、学习、培训、敏捷开发等方面还是一个比较折中的选择（主要在于人，而不是语言）。
python，ruby之类的动态语言优势在于其生产力，你能在极短时间内就搭建出原型从而赢得产品竞争。
推荐一下几本个人认为比较好的Python书籍:

* `《python-guide》 <http://docs.python-guide.org/>`_ requests作者写的guide，偏向工程方面

* `《use python》 <http://use-python.readthedocs.io/zh_CN/latest/>`_ use python

* `《A Byte of Python》 <http://python.swaroopch.com/>`_ 一百多页的小书，可以快速熟悉Python语言。

* `《Python核心编程》 <https://book.douban.com/subject/26801374/>`_ 比较全面的Python书籍，介绍了Python语言的方方面面。

* `《Dive Into Python》 <http://www.diveintopython.net/>`_ 一本免费的开源书

* `《Fluent Python》 <https://book.douban.com/subject/26278021/>`_ Python进阶的好书，没有之一，涉及了很多Python高级主题和实现特性。

* `《Python3 Cookbook》 <http://python3-cookbook.readthedocs.io/>`_ Python进阶读物，汇集了很多技巧。

* `《Python高级编程》 <http://dongweiming.github.io/Expert-Python/>`_ 豆瓣工程师董伟明先生写的python高级编程 ppt


当然还有Python的官方文档作为参考，不过有些文档比较晦涩，还是推荐书籍入门。网上目前也可以搜到很多免费的电子书。
如果有时间可以看看国内廖雪峰写的Python教程，简单易懂，就是跳跃有点大（有些章节对新人来说不是很友好）。


算法与数据结构
----------------------------
编写良好的代码需要了解常用的算法和数据结构，虽然你可能很少会自己实现，但是对于Python语言中一些常用数据结构如list, tuple, set, frozenset, dict和collections模块中的OrderedDict, defaultdict, deque, namedtuple, Counter等应该知道什么时候用。最主要的还是了解算法中递归，二分等常用思想，写出高效易用的代码。如果你想在线练习，可以做一些Acm基础题或者去leetcode等网站刷题。
推荐书籍:

* `《算法导论》 <https://book.douban.com/subject/20432061/>`_
  你可以挑选感兴趣的章节啃一啃，也可以去网易公开课看下视频教程。如果不是计算机专业的可以看下《计算机科学导论》这门公开课，正好也是以Python语言讲解的。


计算机网络
----------------------------
对于应用开发者来说大部分时间可能不太会接触特别底层的问题，但是了解网络的运行原理还是必要的。网上有个面试题  `从输入URL 到页面加载完成的过程中都发生了什么事情？ <http://fex.baidu.com/blog/2014/05/what-happen/>`_ 如果对其中大部分的概念都了解就算是入门了。网络相关书籍可以随便找一本看看。Http协议对于web开发者来说比较重要，需要深入了解。推荐书籍:

* `《图解Http》 <https://book.douban.com/subject/25863515/>`_
  一本小白入门Http协议的好书，有大量图片示例。
* `《Http权威指南》 <https://book.douban.com/subject/10746113/>`_
  Http协议最权威的讲解，大部头著作，可以看看最基础的部分。
* `《网络爬虫教程》 <https://piaosanlang.gitbooks.io/spiders/01day/README1.html>`_
  非常不错的爬虫教程。感谢原作者，其实感觉这种把学习的内容总结成小书的方式很好。
* `《Python3 网络爬虫实战》 <https://germey.gitbooks.io/python3webspider/>`_


Linux系统
----------
大部分Python应用都是跑在Linux服务器上的，大部分开源服务器软件使用的也是linux系统，即使日常工作不使用linux，一些基本的linux命令也要了解。
比如常用的文件操作，目录操作，进程操作等。你可以使用类unix系统mac或者linux版本ubuntu作为学习环境。
推荐：

* `《Linux工具快速教程》 <https://linuxtools-rst.readthedocs.io/zh_CN/latest/>`_
* `《CONQUERING THE COMMAND LINE》 <http://conqueringthecommandline.com/book/>`_
  掌握这上面的命令基本就可以满足日常需求了。
* `《鸟哥的Linux私房菜.基础学习篇》 <https://book.douban.com/subject/4889838/>`_
  浅显易懂，入门Linux命令的好书。


数据库
----------
现在网站业务后端用得比较多的有三种类型的数据库，关系型数据库（mysql等），文档型数据库（mongodb等），和内存型数据库（redis等）。三种数据库各有优势和其使用场景，后端程序员需要了解下不同类型数据库的使用方法和应用场景，灵活应用到后端代码中。关于各种数据库网上已经有不少资料，读者可以自行搜索学习，比较重要的是 mysql 和 redis。
对大数据感兴趣的可以学习下 Hadoop生态系统。

* `《Designing Data-Intensive Applications》 <https://book.douban.com/subject/26197294/>`_
  了解各种数据存储模型，本书覆盖面很广，适合有一定基础的人阅读


python 相关库的使用
-------------------
python一大优势在于数量丰富的库，灵活使用各种python库能帮助我们快速做出产品。作为web开发者，你需要了解常用python库和框架的使用，比如django/flask/tornado/sqlalchemy/requests/pandas等。

web 框架
-------------------
大部分后端业务逻辑开发中都会使用 web 框架，提升开发效率。常用的 python web 框架有 Django、Flask、Tornado 等，一般 web
框架都包含 http 处理、表单验证、模板引擎、ORM 、Restful 接口等，最好能熟练掌握一个 web 框架，帮助快速做出产品。

版本控制
----------
目前最流行的应该就是git了。版本控制工具是多人协作必不可少的工具，入门的程序员需要掌握基本的git命令，可以把github作为个人练习的工具。

* `《语义化版本控制》 <http://semver.org/lang/zh-CN/>`_
* `《Pro Git》 <https://git-scm.com/book/en/v2>`_

Web 服务器
----------
Nginx 目前很流行，使用比较广泛，推荐学习和使用。熟悉基础的 LNMP 架构(Linux + Nginx + Mysql + Python)，目前很多公司采用了都是多语言+微服务架构(基于 docker)。
你可能需要了解常见的 web 应用部署方式以及如何使用 ngxin 等负载均衡

前端知识
----------
基本的 html，css，javascript 需要有所了解。很多后端工程师需要做一些工具或者管理后台之类的，了解前端知识会有帮助。

学习和搜索能力
--------------
初学者碰到的大部分技术问题都是可以通过 google 解决的，用好 google/stackoverflow/github 和各种技术论坛、牛人博客等能帮助你了解最新的技术。

* `《Instagram Engineering》 <https://engineering.instagram.com/>`_ Instagram 技术博客，有不少 python 相关的技术文章


业务领域知识
------------
不同公司业务不同，经营（挣钱）领域不同（游戏、广告、媒体、社交、金融等），可能需要了解相关领域知识，方便业务建模。建议找工作之前研调下相应公司、经营领域、使用的技术栈等，不要太盲目，找到自己感兴趣的方向(后端知识很广)，有时候方向和平台很重要，直接决定了你的工资和发展。

专业素养
----------
公司做项目不是自己过家家，需要你具备写文档，注释，单元测试，沟通表达、与人协作、处理业务的能力。如果你现在还不了解一个正规python项目都有哪些组建构成，请去github克隆一份知名的代码仓库，花点时间仔细分析下它的项目结构和源代码。
比如著名网站reddit代码已经开源，大部分python实现，可以参考下。另外很多著名的python库，比如requests/flask等也可以作为参考。从笔者短暂的从业经历来看，大部分自学python的人不怎么遵守代码规范（pep8），
不知道或者不重视单元测试（写个函数print下就觉得OK了），不知道怎么写注释和文档（docstring听过吗？）。所以希望学习python的你能遵守工程实践，具备良好的职业素养和编码习惯，推荐阅读《代码大全》《编程匠艺》之类的工程相关的书。

* `《程序员的职业素养》 <https://book.douban.com/subject/11614538/>`_

后端技术栈
----------
对于技能需求可以在拉勾上搜一下Python的职位，看看各个公司对Python的要求。或者你可以写个拉勾网的爬虫，对数据做一个简单的统计，笔者当初找工作就是这么干的。找工作之前最好研究下期望公司的业务和使用的技术栈，有针对性学习。
另外，真正做项目还需要你熟悉python的各种库和框架，比如django/flask/tornado/requests/sqlalchemy/unittest/celery等等，掌握了合适的工具才能快速上手做东西，公司恨不得你第一天入职第二天就能写项目。
所以，在你入了门以后请尽快熟悉python web的技术栈。公司不管你会什么算法，只在乎你的生产力(有时候技术本身不重要，它的价值在于对业务、用户、顾客的贡献)。
推荐一些文章供参考:


* `《全栈增长工程师指南》 <https://github.com/phodal/growth-ebook>`_
* `《web开发路线图》 <http://skill.phodal.com/>`_
* `《后端都要学习什么？》 <https://www.zhihu.com/question/24952874>`_
* `《PYTHON招聘需求与技能体系》 <http://www.wklken.me/posts/2013/12/21/python-jd.html>`_
* `《PYTHON后端相关技术/工具栈》 <http://www.wklken.me/posts/2014/07/26/python-tech-stack.html>`_


学习路线
----------
看了这么多是不是还有点懵，笔者当时自学的时候也没人带，没什么方向，走了很多弯路，找工作也不是一帆风顺。如果不是科班出身受过系统的计算机科学理论的训练，是比较吃亏的，只能通过大量针对性学习和练习来弥补。
大概整理下自己学习 python web 的路线，方便大家做个参考(一个合格的工程师不是短时间能练成的)。其实这基本上也是后端工程师的学习路线，换一个编程语言或者框架都差不多。

- 学习并熟练掌握一门编程语言。这里笔者选择的是最近特别火的 python，它能干很多事。挑一本好的入门教材，通读并实践书中所有代码示例和练习题（练手感，坚持敲，大量敲）。了解该语言如何操作文本、进程、文件等，最后达到能熟练运用编程语言表达逻辑、写脚本的能力。
- 搭建好开发环境。初学者个人比较推荐 Ubuntu 系统 + Pycharm 社区版，都是可以免费获取的，我经常安利用 linux 或者 mac，因为企业大部分用的都是 linux server 部署 web 应用的，熟悉 linux 命令行、文件、进程操作等会给你找工作和日常工作带来便利。
- 熟悉算法和数据结构。对于编程语言内置的数据结构、算法等要数量掌握和使用，常用数据结构和算法了解其原理，会计算时间空间复杂度，会自己实现(常见算法面试笔试常考)。
- 熟悉网络协议 TCP/IP，HTTP，了解互联网是怎么运作的。既然是做网站，需要对网络运行原理比较了解。
- 学习 web 框架和 python 库。做东西我们需要大量现成的轮子帮助我们，看下 django、flask 等流行的 tutorial，然后做个简单的网站出来（比如博客网站）。最好能深入一个框架了解原理，比如看看 flask 和 Werkzeug 源码。
- 了解前端知识。如果能独立做一个博客出来，大概对 html、css、js 就有所了解了。虽然是做后端，但是基本的前端知识也是必不可少的。
- 学习业务常用数据库 mysql 和 redis，业界用得比较多的数据库。了解关系型数据库 mysql 基础概念、语句、索引优化等，了解内存型数据库 redis 的常用数据结构，使用场景、结构设计等。
- 学习 git 版本控制。公司项目协作的时候都是有版本控制的，方便我们协作、记录、回滚代码等。
- 在 linux server 部署你的 python web 服务。你需要学习 linux 常用命令，web 服务器 nginx 等。最好能独立部署一个网站出来。
- 对照招聘网站中意的公司的招聘需求查漏补缺。初期就是要多学多练多 google，不是做项目就是在刷题。

系统设计进阶
------------
对于有经验的工程师来说，系统设计也是一项重要的能力（也是除了存储系统、程序设计、网络通讯、操作系统之外经常被面试考到的）。比如设计一个短网址服务、简单的 feed 流系统、推荐系统、发号器服务等。笔者也处于学习中，推荐个资料供参考：

* `《https://github.com/PegasusWang/system-design-primer》 <https://github.com/PegasusWang/system-design-primer>`_ 关于系统设计和架构设计相关的资料
