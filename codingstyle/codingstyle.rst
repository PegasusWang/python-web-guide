.. _codingstyle:

编码之前碎碎念(工程实践)
=====================================================================

..

  Controlling complexity is the essence of computer programming.  — Brian Kernighan

有些人喜欢动态语言的表达能力和灵活性，有些人却讨厌动态语言，认为动态语言工程不友好，性能低、易出错、难重构。在项目中应该结合不同语言的生产力、性能、生态圈、招聘需求、产品周期等，灵活选取，扬长避短。
动态语言比较适合构建 mvp（最小可用产品），所以很多创业公司后端、内部项目、微服务等在用。以下是笔者从业过程中总结的一些工程实践，因为动态语言本身的特性，需要良好的工程控制保证代码质量，否则将来项目代码仓库可能会失控。
前目网上关于 python 项目工程的资料比较少，仅供参考。


代码风格
--------------------------------------
不一致的开发风格会给协作开发带来困难，同时也妨碍代码阅读，读代码的时间是远多于写代码的，所以有必要统一编码规范。推荐使用pep8或者其子集作为代码规范，使用vim插件python-mode开启pep8和pylint对代码静态检测。如果使用其他编辑器或者IDE工具最好也使用相关插件使代码符合规范。工程上的代码应该尽可能保持清晰易懂，推荐看看requests等优秀的开源库学习下。强烈建议新手看看以下参考写出格式规范的代码，强烈建议打开pep8和pylint，pylint可以帮助你干掉很多低级错误。建议使用py的公司都指定好自己的代码规范并且严格遵守，同时做好code review，防止造成以后的维护噩梦。

* `《PEP8.org》 <http://pep8.org/>`_
* `《PEP 8 -- Style Guide for Python Code》 <https://www.python.org/dev/peps/pep-0008/>`_
* `《Google开源项目风格指南-Python风格指南》 <http://zh-google-styleguide.readthedocs.io/en/latest/google-python-styleguide/contents/>`_ google风格的docstring比较赞
* `《API_coding_style》 <http://deeplearning.net/software/pylearn/v2_planning/API_coding_style.html>`_
* `《code-example》 <https://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html>`_
* `《编写优雅代码》 <http://www.kancloud.cn/kancloud/sina-boot-camp/64003>`_  新浪微博的培训课程，可以学习一下
* `《烂代码的那些事》 <http://blog.2baxb.me/archives/1343>`_  Axb的自我修养，大神的文章
* `《三种docstring示例》 <http://bwanamarko.alwaysdata.net/napoleon/format_exception.html>`_
* `《Simple python style guide》 <http://liyangliang.me/posts/2015/08/simple-python-style-guide/>`_
* `《python编程规范》 <http://blog.ganyutao.com/downloading/python%E7%BC%96%E7%A8%8B%E8%A7%84%E8%8C%83.pdf>`_


一个简洁的代码规范(想偷懒的话直接用pylint 和 autopep8 过一遍):

- 格式请遵守pep8,务必开启编辑器的pylint和pep8检测。vim请试试python-mode插件，现在不过一下 pylint 都不太敢提交代码了，动态语言太容易出错。
- 业务逻辑应该限制一些过于灵活的特性，防止代码难以维护。比如元编程，随意的设置属性等，尽量保持业务代码易维护、易修改、易测试。
- 模块、类和函数请使用docstring格式注释，除显而易见的代码，每个函数应该简洁地说明函数作用，函数参数说明和类型，返回值和类型。对于复杂的传入参数和返回值最好把示例附上。如有引用，可以把jira，github，stackoverflow，需求文档地址附上。 良好的文档和注释很考验人的判断（何时注释）和表达能力（注释什么）。
- 动态语言的变量命名尽量可以从名称就知道其类型，比如url_list, info_dict_list，降低阅读和理解的难度。(我的感觉就是动态语言易编写，写不好后期更难维护)
- 风格上衡量不了请参考知名开源项目的做法。以可读性和维护性作为标准。(比如知名网站reddit的python代码已经开源了，可以作为参考，强烈建议大家克隆一份，经常拉取更新，看看人家怎么写的python代码)
- 阿里最近开源了一个规范《阿里巴巴Java开发手册》，网上可以很容易搜到，写得比较细，建议新手下载来看看，有不少实战干货，很多思想是通用的，其实python的unittest等模块很多都是直接借鉴了java。还有新浪微博的《新兵训练营系列课程》
- 给一些小团队的建议就是所有人统一用 pylint 和 autopep8 工具， pylint 检测代码有没有明显缺陷，autopep8 用来整理格式(类似于 golang 的 gofmt)，至少在风格上就不用在费心统一格式了，代码洁癖必备。

* `《Python 项目工程实践》 <https://zhuanlan.zhihu.com/p/32902344>`_  如何通过工具构建良好的工程代码
* `《Python 工匠：善用变量来改善代码质量》 <http://www.zlovezl.cn/articles/python-using-variables-well/>`_ 动态语言命名尽量可以表达出类型，否则不好维护
* `《Python最佳实践》 <http://www.dongwm.com/archives/Python%E6%9C%80%E4%BD%B3%E5%AE%9E%E8%B7%B5/>`_  董伟明的文章
* `《PYTHON 代码规范小结》 <http://www.wklken.me/posts/2016/11/03/python-code-style.html>`_

编程范式
--------------------------------------
Python支持多重编程范式，过程式(Procedural)，面向对象(OOP)，简单函数式(Functional)编程。不同人，不同语言转过来的人，Python老鸟和菜鸟等写出来的代码风格迥异。对个人风格喜好不予评判，但是个人感觉还是需要深挖一些Python的特性，虽然Python容易入门，但是有些语言特性还是需要一段时间才能了解深入的。使用各种风格的时候要酌情判断，比如多个过程需要共享中间状态时，单纯的使用函数会写得很冗长，这时候就应当使用类。通常能用函数完成功能的就使用函数。当你无法判断哪种方式比较好的时候，请在解释器里边 `import this` 看看。当可以实现一样的功能时，往往简单易懂的方式就是最好的。一些参考:

* `《requests》 <https://github.com/kennethreitz/requests>`_ requests库是接口设计的典范，可以参考参考。
* `《Python3 面向对象编程》 <https://book.douban.com/subject/26468916/>`_ 关于Python面向对象和一些设计模式。
* `《OOP vs Functional Programming vs Procedural》 <http://stackoverflow.com/questions/552336/oop-vs-functional-programming-vs-procedural>`_


何谓Pythonic?
--------------------------------------
Python的世界里你会听到这个词"Pythonic"，大概就是指代码符合Python的惯用法，使用的都是Python的语法糖(我觉得可以翻译为『地道』)。比如从其他语言转到Python
的写出来的代码很可能受到以前思维方式的影响(别像 java 一样写一堆 getter/setter)，写出来的代码不够Pythonic:
比如:


.. code-block:: python

    # 不够Pythonic
    if a < b and a > c:
        pass

    # python里却可以这么写
    if c < a < b:
        pass

    # bad
    i = 0
    while i < mylist_length:
        do_something(mylist[i])
        i += 1

    # good
    for element in mylist:
       do_something(element)

    # bad, 不要使用默认可变对象作为默认参数
    def f(a, b=[])
        pass

    # good, 可变类型使用 None 作为占位符
    def f(a, b=None):
        if b is None:
            b = []


Python有一些语法上的坑，比如默认参数只计算一次，不要使用可变类型作为默认参数等，看多了写多了就知道了。尤其是可变类型作为函数参数传入后被改变的情况（函数尽量不要有副作用,这里副作用指的就是修改了传入的可变参数的值），尤其要注意。
一些参考帮助写出Pythonic的代码（注意pythonic 不是要你炫耀奇淫技巧，维护起来心累）:


* `《Transforming Code into Beautiful, Idiomatic Python》 <https://gist.github.com/JeffPaine/6213790>`_
* `《Pythonic到底是什么玩意儿？》 <http://blog.csdn.net/gzlaiyonghao/article/details/2762251>`_ 赖勇浩的博客
* `《python-guide Code Style》 <http://docs.python-guide.org/en/latest/writing/style/>`_ python-guide关于代码风格的介绍
* `《Learning the Pythonic Way》 <https://www.cs.cmu.edu/~srini/15-441/F11/lectures/r04-python.pdf>`_ 一个cmu的课件
* `《Writing Idiomatic Python3》 <http://share.sm3.su/writing_idiomatic_python_3.pdf>`_ 一本免费小书
* `《编写高质量代码：改善Python程序的91个建议》 <https://book.douban.com/subject/25910544/>`_ 给国人的书捧捧场^_^
* `《Code Like a Pythonista: Idiomatic Python》 <http://python.net/~goodger/projects/pycon/2007/idiomatic/handout.html>`_  我强烈推荐新手看看这个教程


敏捷与TDD
----------------------------
笔者非计算机科班出身，对于软件工程的东西也不是很懂，最近扫了一本《敏捷软件开发-原则、模式与实践》，感觉有些东西还是挺有启发的。在这里稍微提一下敏捷中的TDD(Test-driven development)吧。因为Python是动态类型语言，不像静态语言可以编译期检查，很多问题运行时暴露出来，而且动态语言语法灵活也容易刨坑。用TDD是可以提升代码质量的，虽然有时候完全用TDD可能有些死板，但是TDD的一些思想还是很值得借鉴：

* 测试最重要的是对架构和设计的影响，不是为了测试而测试。一般难以测试的代码往往是设计不好，耦合严重的代码。没有测试的代码同时也给重构带来压力和隐患。

编码的时候想着如何测试它，甚至都可以改善设计。对于动态语言，一直有『动态语言一时爽，代码重构火葬场』这种说法，说明动态语言如果没有良好的设计和测试，以后是会埋下不少隐患的。
当你发现debug的时间甚至比写代码长很多的时候，当你发现总是返工对代码修修补补的时候，或者可尝试下TDD。
你可以学习使用下python的unittest或者pytest等进行单元测试，以保证代码质量。个人工作经验也表明，难以测试的代码往往是设计不太好的代码。
update: 经验表明，TDD未必是必要的，但是单元测试是很必要的。如果是新项目建议为所有的复杂函数写单元测试，为项目质量保证。大项目如果没有单元测试修改bug和重构会有很大风险。
另外一般写测试之前先写个失败的例子(比如我会在测试函数开头加上 assert 0 失败一下确保我这个测试函数真正跑了的，我见过不止一次由于命名没有加test开头压根就没跑测试函数的，还以为测试通过了)，确定测试是真正运行了的，因为之前出现过乌龙，单测函数命名没有用 test 开头结果导致根本就没有运行这个测试用例，后来修正了以后跑失败了，如果先失败一次就会避免这个问题，说白了就是保证你的测试用例确实是跑了的。
感兴趣可以试试极限编程中的测试驱动开发和结对编程。
下边是一些参考:

* `《COMPREHENSIVE GUIDE TO CODE QUALITY: BEST PRACTICES AND TOOLS》 <http://codingsans.com/blog/code-quality>`_
* `《敏捷开发的艺术》 <https://book.douban.com/subject/4037534/>`_
* `《敏捷技能修炼》 <https://book.douban.com/subject/11614307/>`_  实践出真知
* `《Tips for agile developers》 <http://web2.0coder.com/archives/92>`_
* `《pytest: helps you write better programs》 <http://pytest.org/latest/>`_
* `《代码整洁之道》 <https://book.douban.com/subject/5442024/>`_
* `《编写可读代码的艺术》 <https://book.douban.com/subject/10797189/>`_ 代码首先是写给人看的
* `《重构-改善既有代码设计》 <https://book.douban.com/subject/4262627/>`_
* `《软件调试修炼之道》 <https://book.douban.com/subject/6398127/>`_ 了解下调试和跟踪技术。
* `《测试的道理》 <http://www.yinwang.org/blog-cn/2016/09/14/tests>`_ 垠神的博客


业务代码的一些常见原则
----------------------------
对于什么是好代码，什么是坏代码我现在还没有太多经验，但是最近工作接手别人的代码感觉困难重重，还是too naive啊。每个人实力不同，风格不同，一起协作的时候确实会遇到很多问题和分歧。感觉code review啥的还是很有必要的，可以让菜鸟学习下老鸟的经验，也可以让老鸟指导下菜鸟的失误，同时避免过于个人化的糟糕风格（比如让人想立马离职的高达成百上千行的复杂函数，比如上来一堆不知道干啥的幻数，比如上来就 `from shit import *` 导致俺的编辑工具找不到定义，比如整个项目没有一行测试代码，比如不知道用logger，全用print+眼珠子瞅，一个bug找半天，比如没有pep8检测导致你的环境打开别人的代码彪了一堆警告......)。

说好的规范呢，说好的设计模式呢，说好的高内聚低耦合呢？说好的KISS原则呢？说好的DYR原则呢？其实俺只是想多活几年，至少不要到三十岁头发掉光。啥设计模式的可以不用，能干活的代码就行，牢记几个原则，没事的时候对复杂的东西重构下，代码不能自解释的搞搞文档，不被队友坑同时不坑队友，俺就心满意足了 ，遇到坑队友就等着加班和折寿吧:(。最后还是列举一下常用原则、思想和注意事项吧(下边原则是笔者阅读很多工程相关的书后总结的，比较宽泛，最好import this看看python之禅，很多思想是通用的):

* KISS原则，Keep It Simple, Stupid。能简单的绝对不要复杂，不要炫耀代码技巧，简单可读最重要，后人会感谢你的，软件构建的核心就是控制复杂度。开发可以工作的、最简单的解决方案。除非有不可辩驳的原因，否则不要使用模式、原则和高难度技术之类的东西。
* DRY原则，Don't Repeat Yourself。代码复杂重复了就及时抽取出来，至少不会碰到大问题。当然不要矫枉过正，过度追求设计和通用可能导致难以维护和理解。重复代码一旦接口变动的时候就是灾难，要修改很多地方，一定要十分警惕代码重复(警惕复制粘贴，往往代码重复是设计、抽象不合理、意图不明确的表现，而且复制代码经常会出现忘记修改一些细节产生 bug)。事不过三原则。Prefer duplication over the wrong abstraction. - Sandi Metz
* YAGNI(You Aren't Gonna Need It)，不要猜测性编码，不用的及时删除，估计以后也不太可能会用到，冗余的无用代码会给维护者带来很多混淆和麻烦。Build the simplest thing that we need right now。『少即是多』
* SLAP(Single Level of Abstraction Principle): 保持一个方法中的代码在同一个抽象层。
* Clean Coder Rule: Always leave the code cleaner than you found it.  不用的代码及时清除，留着只会造成冗余和误解(如果你认为某段代码将来可能会用到，我明确告诉你基本上它是用不到的)。笔者经验是用动态语言写代码很难写出 clean code，必须上各种静态检测工具和规范来约束，防止代码腐化。
* 快速失败，灵活使用断言。契约式编程(先验条件和后置条件)，越早失败，越容易排查错误。
* 增量式编程。及时清理技术债务，代码坏味道，防止『破窗』。及时重构不合理代码，及时进行测试，『慢即是快』，越早发现错误修复成本越低。很多统计数据的结果都显示，一名程序员在公司每天能产出的工业级别的代码不会超过百行。
* 隐藏复杂性。如果复杂性避免不了，应该尽让内部复杂，接口要保持简单易用，而不要因为业务逻辑复杂就堆砌一堆shit。合理抽象，隐藏细节。
* 一次只做一件事(Do one thing, and do it well)。尽量避免复杂度过高的逻辑，尽量做到代码简单，意图明确。
* 高内聚，低耦合。模块化。层次化。意义相近的东西应该放到同一个地方。写代码的时候想着怎么测试它就能避免过度复杂，耦合严重的代码。
* 代码应当易于理解。 《代码大全》、《编写可读代码的艺术》、《代码整洁之道》啥的都是告诉你代码最好自解释，好理解。记住代码首先是给人看的，其次才是让机器执行的，不要过度设计。同时警惕你觉得过于『精巧』的实现，很有可能成为以后代码维护的大坑。可读性基本定律：代码的写法应该使别人理解它所需的时间最小化。聪明的程序员可能写出复杂、精巧的代码(但是对于整个团队的维护来说未必是好事)，专业的程序员会写出可读性高的代码。
* 不要过早优化，最小可用原则。先测量(profiler)，后优化。根据二八定律，大部分性能瓶颈只在20%的部分，这些才是真正需要优化的地方。不要一开始写代码就极力想压榨所有性能，往往引入优化的同时也在引入风险、复杂度和难以调试的 bug。
* 不要炫技，可读性最重要。合适的地方使用合适的技巧，不要过度炫耀语法糖导致维护和理解困难。大部分人不是造轮子的，你用不着太多奇淫技巧。
* 不要重复发明轮子(除非你是在练习编程)。遇到问题首选稳定可靠的解决方案。比如处理excel报表等直接用pandas提供的函数非常方便，我经常看见还是有人自己写一堆恶心的处理函数而不用pandas。如果自己造轮子确保测试和文档，否则后续维护和上手会有很大成本。
* 自动化。重复执行的任务应该使之自动化，你用的python是写自动化脚本最合适的语言。
* Think about future, design with flexibility, but only implement for production. 尽量设计良好，避免繁杂和冗余。好的架构和设计都是不断演进的。
* 文档化。哪些东西该文档化，哪些该注释需要做好，以便新手可以尽快上手。尽量做到代码即文档，tornado的文档和代码就是典范。
* 服务化。项目做大了以后及时拆分业务，保持单个代码仓库大小在一定规模。超大规模的代码仓库在部署和维护上会遇到很多问题。
* 不要直接吞掉任何非预知错误和异常，一定要做好记录。血泪教训，使用Sentry或其他工具记录好异常发生的信息，为定位bug提供便利，web端的bug一般不好复现。
* 墨菲定律：只要有错误发生的可能性，这种错误就一定会发生。所以对代码质量要严格要求，不要心存侥幸。
* 单元测试:F.I.R.S.T原则(Fast，Independent，Repeatable，Self-Validating，Timely)
* ......还有的大家可以自己补充。我强烈建议新手或者自学的同学看《代码大全》或者《编程匠艺》之中的任何一本，带你快速入门。当然有些东西只是建议，编程中往往没有绝对正确(不要过度迷信某些所谓的实践和原则)，只有相对更优，No Silver Bullet，大家在实践中摸索吧。

`《编程到底难在哪里？》 <https://www.zhihu.com/question/22508677>`_

`《Unix 编程艺术》 <https://book.douban.com/subject/1467587/>`_   如果你有时间可以当成小说看看，感觉有点宗教主义


还有OOP那一套，当你设计一个类的时候需要有所注意(SOLID原则):

* 单一职责原则(Single-Responsibility Principle): It should have a single purpose in the system, and there should be only one reason to change it.
* 开闭原则(Open-Closed Principle): 对修改关闭，对扩展开放。Code should open to extension but closed to modification.
* 里氏代换原则(Liskov Substitution Principle): 所有使用基类的地方都可以使用子类替换。Anywhere you use a base class, you should be able to use a subclass and not know it.要遵守Liskov替换原则，相对基类的对应方法，派生类服务（方法）应该不要求更多，不承诺更少。
* 接口隔离原则(Interface Segregation Principle): 不要强制客户端使用他们不需要的接口。Don't force clients to use interfaces they don't need.
* 依赖倒置原则(Dependence Inversion Principle): 高层模块不应该依赖于底层模块，他们都应该依赖于抽象。 High-level modules shouldn't rely on low-level modules, both should rely on abstractions.
* 迪米特原则(Law of Demeter):
* 合成复用原则(Composite/Aggregate Reuse Principle):

`《如何在Python里应用SOLID原则》 <http://aju.space/2016/06/17/use-S-O-L-I-D-in-python.html>`_

Unix 哲学(来自《Unix 编程艺术》)，如果你对 unix/linux 的设计哲学和发展历史感兴趣可以看看这本书（我经常安利后端开发者使用 mac/linux 系统，它们在学术界和工程界更受欢迎）：

* 模块原则：使用简单的接口拼合简单的部件
* 清晰原则：清晰胜于机巧
* 组合原则：设计时考虑拼接组合。组合优先于继承
* 分离原则：策略同机制分离，接口同引擎分离
* 简洁原则：控制复杂度
* 吝啬原则：除非却无它法，不要编写庞大的程序
* 透明性原则：设计要可见，以便审查和调试
* 健壮原则：健壮源于透明与简洁
* 表示原则：把知识叠入数据以求逻辑质朴而健壮
* 通俗原则：接口设计避免标新立异
* 缄默原则：如果一个程序没什么好说的，就缄默
* 补救原则：出现异常时，马上退出并给出足够的错误信息
* 经济原则：宁花机器一分钟，不花程序员一秒
* 生成原则：避免手工hack，尽量编写程序去生成程序
* 优化原则：雕琢前先要有原型，跑之前先学会走
* 多样原则：绝不相信所谓『不二法门』的断言
* 扩展原则：设计着眼未来，未来总比预想来得快

python代码坏味道(新手经常犯的错误)
--------------------------------------
下边是笔者学习和维护代码的过程中总结的一些经验和发现的一些问题，可能有些地方会有分歧，python在工程实践方面的资料不如其他语言那么成熟，仅供参考：

风格相关:

- 不pythonic，写得很业余(随意)，真就信了半天学会python。笔者写代码强制用pep8和pylint检测代码(集成到编辑器里)，除了一些无伤大雅的提示（比如行长度超过80），其他错误和提示全部消除。一开始比较痛苦，习惯了能大幅提升代码规范性。
- 千万不要硬编码，上来就整一个不知道啥意思的magic number or string，大学老师没教你不要滥用幻数(if status=1，来告诉我1是啥意思)？千万不要借鉴谭浩强那套教材里的编程风格，使用Enum或者dict或者对象都能替代掉无意义的幻数。总有人偷懒使用幻数，别人看懵逼的。
- 上来就 `from shit import *,` 为了偷懒有可能会导致同名覆盖问题，还会让开发工具找不到定义，工程上不要这么用。
- 包导入顺序混乱，没有按照pep8要求，实际上rope等工具能自动帮你整理顺序，我现在就是偷懒随意写，直接让rope给我整理。(标准库，三方库，本地库，同级按照字典序，vim的话可以用rope插件自动整理顺序)
- 导入最好按照模块导入，使用的时候用module.func使用，防止from module import func的时候可能遇到的循环引用问题(模块设计不够合理)。
- 变量名乱起，表意不明，推断不出类型，加重理解负担。我在想是不是动态语言用匈牙利命名法要好一些，命名尽量要可以看出类型，比如复数表示容器类型，nums，cnts等后缀表示数值(通过后缀和词性来使名称更容易被推断出来含义)。动态语言一大诟病就是容易类型出错。
- 不遵守pep8，没有pylint检测，打开代码一堆语法警告，老子的编辑器满眼都是warnning，编辑器用不好就老老实实用pycharm，用编辑器就老老实实装好语法检测(pep8)和pylint检测插件，没有插件请考虑换一个editor。我个人的感觉就是python代码很容易写得难以维护，请务必加上pylint检测，帮助提高代码质量。还是推荐不想折腾编辑器的直接用好pycharm。
- 没有逻辑分块，一点都不重视排版，没有美感（这个就算了），就算不限制一行超过80列，也不能写一行写几百列吧，左右转头脑瓜子疼(请不要用tab，全用空格，不要有多余空白，vim有类似插件去除无用空白的)。使用良好的分行，空格使代码更美观，逻辑更清晰。
- 不要一行写太多逻辑，比如嵌套的列表推导。(Raymond's rule: One logical line of code equals one sentence in English)。好的代码读起来应该和读英文差不多，从上到下知道每一步都干了什么。不要轻易为了代码技巧缩短行数，易读性更重要。业务代码能不用奇淫技巧就千万别用，维护起来心累。
- 统一编辑环境（editorconfig）、导入顺序（isort）、编码规范（autopep8）、静态检测（pylint），甚至统一命名规范和名词术语（不要相信各种中式英语，换一个人就看不懂了）。

* `《https://docs.python.org/3/faq/programming.html#what-are-the-best-practices-for-using-import-in-a-module》 <https://docs.python.org/3/faq/programming.html#what-are-the-best-practices-for-using-import-in-a-module>`_
* `《https://docs.python.org/3/faq/programming.html#how-can-i-have-modules-that-mutually-import-each-other》 <https://docs.python.org/3/faq/programming.html#how-can-i-have-modules-that-mutually-import-each-other>`_
* `《unmaintainable-code》 <https://github.com/Droogans/unmaintainable-code>`_ 从反面教材学习如何编写 maintainable code

异常相关：

- 到处print，debug的时候加上，上线再删除（累不累亲？），logging模块很受冷落
- 上来就try/except了，把异常都捕获了，吞掉异常导致排错困难。就在我写这段的时候又因为使用了他人未经测试的代码排错许久，就是因为吞了异常没打出来异常信息。
- 捕获的异常应该尽量类型精确，范围清晰。不要上来就try一整个代码块，可以继承内置异常类定义自己的更为精确的异常类。
- 使用sentry等工具记录异常，有利于排查问题(能保存堆栈和现场信息)。切记不要轻易吞掉非预知异常，一旦出现问题不好排查，笔者之前维护的项目曾踩过坑，后来笔者引入了sentry排查问题方便很多。
- 捕获异常是为了处理它，确定要怎么处理异常，记录待修复？流程控制？交给上一层重新抛出(raise)？预知异常直接pass？
- 了解你所使用的类库函数会抛出哪些异常，需不需要捕获异常？自定义函数抛出的异常最好在docstring里写出来。
- 编写异常安全的代码: 即使发生了异常，也不会发生异常情况。比如，不会在数据库插入垃圾数据，不会异常终止等。
- 不应当处理超出必要范围的异常，完全预测发生的异常是很困难的，应该抛出给上层程序处理。


模块相关：

- 导入模块，防止代码结构层次设计不合理导致循环引用
- 注意模块尽量不要和标准库或者第三方库冲突
- 注意子模块名称不要和上层模块冲突,否则会 "Import Error: Cannot import Name XXX"。也可以用 `from __future__ import absolute_import` 解决，默认会从顶层包查找。


函数相关:

- 复杂函数没有docstring，接口易用性极差，传入了一个嵌套字典都不注释，娘来。python没有类型声明真是维护代码的一个大坑。
- 保持函数参数和返回值尽量使用简单数据类型，你传入dict或者对象不写docstring我知道字典有哪些字段(最坑爹的是动态语言你还没法跳转过去看参数 object 定义)？如果传入了复杂的参数或者返回类型，最好加上 docstring 说明。看别人代码最头疼的就是看不出参数传的啥结构，返回啥结构，尤其是动态语言，十分隐晦。所以除非必要，保持参数类型尽量简单。
- 函数要么修改传入的可变参数，要么返回一个值。请不要两者同时做。注意python默认参数只计算一次，如果默认参数不是immutable对象，最好使用None作为占位符。每次修改传入的可变参数之前要三思，出bug了不容易排查。注意 None 和 空值的差别，None 是单例的，用 is 来判断一个对象是否是 None。我们能写纯函数就用纯函数（返回结果只依赖于参数并且没有副作用的函数），不容易出错。
- 超长函数，没有复用和拆分，抱歉我智商低，不能理解好几屏都翻不完的，见谅。这么长居然还tm能工作，牛逼(我发现越是新手写的代码越难理解,我实习那会总被说代码写得像面条)。控制复杂度，程序的复杂性决定了一个人要花多大努力才能理解程序。Dijkstra说过『一个聪明的程序员总是清楚地知道自己的脑力容量有限，因此他得十分小心谨慎地完成编程任务』。这不意味着为了处理复杂问题你得增大你的脑力，而是说你得想尽办法尽可能降低复杂性(彻底理解你要解决的问题)。要认识到人的脑力负荷是有限的，凡是你现在绞尽脑汁写的shit 一样的代码，将来维护起来都要花数倍的精力。如果遇到过长的代码，不如把逻辑分为几块，然后每一块抽出来作为函数并且合理命名，这样就容易理解了，别堆砌一长坨。
- 函数『圈复杂度』太高，一堆嵌套逻辑判断，导致测试难以覆盖到所有分之，单元测试几乎就没法写，恩，你压根不写单元测试就当我没说。比如你可以用德摩根律、表驱动法替代过多if/else判断，每当你写下一个if的时候，确定是否需要对应的else。感兴趣的可以搜搜软件工程里关于圈复杂度的概念，降低复杂性是编写高质量代码的关键。也可以尝试用结构化编程、单出口等方式降低代码出错率。
- 穿插着让人摸不着头脑的代码片段。（对于变态的产品需求或者非常triky的代码必须加上注释）。个人非常推崇『意图导向』编程，就是每写下一个块模、函数、类、代码片段的时候，除非显而易见或者约定俗成，否则都注释上你为什么需要它、它在哪里会用到。如果所有代码都得通读一边才能知道它是干啥的，是非常耗时的。(笔者挺痛恨阅读动态语言写的代码)
- 没注意可变类型和非可变类型，传入可变类型并在函数里修改了参数(无意的修改)，坑。。。还有一种坑 `a = b = c = [] or a, b, c = [], [], []` ，注意可变类型会引用同一个对象，注意 python 中的深浅拷贝，可变与非可变对象。
- 滥用 `(*args, **kwargs)` 导致函数接口模糊，有类似接口应该明确用docstring写明需要传入什么参数，"Explicity is better than implicity"，不要为了偷懒把代码写得隐晦。请尽量使用简单参数类型并保持接口清晰。
- 返回多个值可以使用namedtuple封装，比用下标更直观。对于可能经常需要变动的返回值，返回字典或者对象要比返回tuple容易修改。但是这种复杂的返回类型最好在docstring里注释下返回结构。适当使用抽象数据类型（ADT）增加代码可读性。
- 减少重复代码，否则将来接口变动一旦修改就要改动很多处，尽量保持函数简短并且尽量复用。
- 注意函数在每个返回点的结构保持一致，尤其是在多个分之有返回点的时候。
- rpc 调用等有没有降级？对方服务跪了会不会影响我们的接口？
- 接口注意几个点，是否代码易读，易用（docstring），正确工作（单元测试）。尽量接口写出来基本就能通过名称和docstring快速让别人知道怎么用的，传入哪些值，返回什么东西，会抛出什么异常。笔者维护代码最最痛苦的就是你得一行一行读代码甚至还得打断点才能搞清楚接口是做什么的(中间充斥者复杂的嵌套数据结构，只有打断点才能看出来)，十分痛苦，十分浪费时间，用python开发省的那点时间全TM用在维护和还技术债了。偷懒只能节省一个人的成本(甚至节省不了)，对项目来说是很不利的。

类相关:

- 你真的需要一个类吗？不要到处OOP，也不要只会写function。你了解OOP的几大原则吗？
- 不要轻易在业务代码中使用元类，也不要轻易在业务代码中过度使用 setattr 等动态特性，可能会给代码维护造成问题。不推荐在业务逻辑中使用黑魔法，以后维护起来简直就是噩梦。
- 保持类的继承层级简单，适当使用mixin。
- 注意不要轻易在非 __init__ 中给类添加属性。
- 尝试使用CRC(clas-responsibility-collaboration)：类-职责-交互卡片设计类。
- 注意多继承时候的 MRO 顺序。
- 保持类的单一职责，不要编写体积过大的类。
- 除非开发框架， 业务里不要使用元类

测试相关:

- 没有单元测试，不知道怎么写测试（print大法好？）。没有一点专业精神，或许和python大部分都是自学的业余选手有关，哈哈当然我也是。没有单元测试对于大项目和动态语言项目来说就是灾难，不敢重构，改bug后无法确认是否引入新bug。对于关键代码一定要保证必要的单元测试。对于喜欢造轮子的，也要保证单元测试。有点违反直觉的是，单元测试长期来看并不会降低工作效率，因为编写代码往往只是工作中一个小环节，很多时间是在调bug，而且没有单元测试几乎不敢重构不好的代码，为代码腐化埋下祸根。但试图编写大量测试会因为工作量大而望而却步，所以可以针对关键和易出错的地方编写必要的单元测试，否则以后修复bug没有测试就是灾难。
- 不专业，写了几句代码print下结果就觉得正确了，单元测试呢？docstring呢？代码易用性和可维护性极差，未经测试的代码是不值得信任的。不要太相信自己，人人都会犯错，但不能反复犯一样的错。
- 对于外部调用、网络请求、rpc调用等使用 mock 或者 stub。

日志相关:

- 哪些地方需要打印日志？debug参数？记录用户行为？排查问题？记录哪些信息？
- 注意日志等级，使用debug/info/warnning/error要斟酌好。

ORM和数据库相关：

- 数据库这一层的接口考虑下参数过滤，防止不恰当参数可能导致的慢查询。
- 优先使用ORM，相比sql语句更加容易维护，同时避免了sql注入。Sqlalchemy只有你想不到，没有它做不到。
- 获取对象的时候尽量传入需要的字段(数据表列)，减少数据传输同时还能避免拼对象的时间消耗，python构建对象比较耗时。
- 注意不要在循环里使用查询语句，合并查询语句。比如不要在for循环中使用一个对象的relation查询(懒加载的时候，每次调用都会查询数据库)
- 注意隐式类型转换导致的全表扫描。大家可以搜一下《数据库30条军规》，有一些坑应该避免。
- 遵守互联网公司数据库设计规范
- Mysql需要存储表情：`CREATE DATABASE mydb CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;`

* `《MySQL互联网业务数据库设计规范》 <https://www.verynull.com/2017/02/18/MySQL%E4%BA%92%E8%81%94%E7%BD%91%E4%B8%9A%E5%8A%A1%E6%95%B0%E6%8D%AE%E5%BA%93%E8%AE%BE%E8%AE%A1%E8%A7%84%E8%8C%83/>`_

文档注释相关:

- 如果是小团队(python大团队感觉会死人的)并且人都比较懒就那就『代码即文档』（有程序员说你让程序员写文档不是天方夜谭吗？你丫的哪个牛逼开源项目的文档是产品经理写的吗？？？excuse me, 代码写不好文档能好看点也行啊，你得让我不看shit一样的代码也能用你的接口啊）。python的特色docstring实际上就是最好的文档。
- 不写注释就得确保你的代码高度可读，不然shit一样的代码又没注释和文档，你让接盘侠怎么活？
- 注释有时候甚至可以帮助你思考设计，比如如果一个类、函数等如果难以用一句话描述它的职责，很有可能就违背了SRP（单一职责原则）。
- 如果系统调用过程比较复杂， 最好用流程图标识一下。
- 对于复杂的数据结构(比如嵌套类型)，可以适当注释出类型，比如最新的 tornado 源码里出现了这种注释 ` __impl_kwargs = None  # type: Dict[str, Any]`  。python3 实际上可以加上类型注解了，鉴于目前 python3 的普及程度，估计暂时也没啥用武之地了。

线程安全相关：

- CPython 实现中，如果内置类型的操作是单个字节码(bytecode)操作，我们可以认为是原子的，操作能保证线程安全。比如 `L[0]=0` 线程安全但是 `L[0]+=1` 不是线程安全的。你可以用 dis 模块来查看操作的字节码。可以认为 GIL 以字节码为粒度。
- 虽然有些操作是原子的，比如字典赋值，但是如果用户自己实现了 `__hash__` 和 `__eq__` python 方法，就变成了非原子的。如果调研后无法确定是否是线程安全，最好使用锁。

* `《Which Python Operations Are Atomic?》 <http://blog.qqrs.us/blog/2016/05/01/which-python-operations-are-atomic/<Paste>`_
* `《Google Python Style Guide: Threading》 <https://google.github.io/styleguide/pyguide.html#Threading>`_

python 代码性能优化相关：

- 不要过早优化，虽然 python 性能一直被诟病。优化之前先使用 profile，火焰图 等工具查看性能瓶颈。基本上代码的耗时是遵守2/8定律的，集中优化最耗时的代码。其实很多 python 内置库都是 c 写的，优化空间并不大。而且大部分 web 应用瓶颈在 IO 这块。
- 在优化和可读性之间寻找平衡。
- 优先从数据结构、算法、数据库等层面优化，大部分 web 应用语言性能不会成为瓶颈。
- 对于 cpu 密集的代码可以使用 cython(不是 CPython) 编写扩展来优化速度，性能提升很明显，在 reddit 和 知乎都有使用；或者使用一些知名库的比如 numpy，pandas处理矩阵等。http://cython.org/
- 更换语言（比如切到 golang），框架（使用异步框架），数据库（Nosql）甚至架构（微服务架构等），成本较高，动作较大，应该是最后的备选方案。
- 常见的 web 后端性能优化措施：

  - 批量：批量接口；消除数据库慢查询等
  - 缓存：使用 redis 等缓存热数据，需要注意缓存失效问题(Cache-aside, Write-through, Write-back)
  - 异步：使用 celery 结合消息队列等把任务交给离线 worker 执行，防止阻塞当前请求。或者使用异步框架，python3 asyncio(至今仍很不成熟) 等。
  - 并发：使用 gevent(greenlet)、多线程 等并发请求数据

* `《常见性能优化策略的总结-美团点评技术博客》 <https://zhuanlan.zhihu.com/p/24401056>`_
* `《High Performance Python》 <http://ningning.today/2017/07/22/%E8%BD%AF%E4%BB%B6%E5%B7%A5%E7%A8%8B/the-art-of-readable-code/>`_
* `《深入理解 Python 异步编程》 <http://mp.weixin.qq.com/s/GgamzHPyZuSg45LoJKsofA>`_
* `《python性能优化》 <http://www.cnblogs.com/xybaby/p/6510941.html>`_
* `《程序员必知的Python陷阱与缺陷列表》 <http://www.cnblogs.com/xybaby/p/7183854.html>`_


嗯，一开始就开启pep8和pylint检测能显著提升代码质量（各种错误警告逼着你写出规范的代码）。咱写不了诗一样的代码，也不能写shǐ 一样的代码，维护一个ugly的代码仓库能有效减少你的寿命。可能很多东西对老鸟来说都是显而易见的，不过菜鸟和高级菜鸟们还是需要多多练习积累经验。慢慢摸索吧骚年。。。。。。如果能主动读一读《代码大全》《编程匠艺》《clean code》《重构》之类的书更好(或者flask等优秀的开源项目代码)，别人会更乐意和你一起合作编程，不然你总会心想『天呐，千万别让我改那个家伙的代码，我宁愿离职！！！』

另外想说的就是，python入门容易，很多人浅尝辄止，但是相对容易出错，想写出高质量的代码反而对人的素养要求更高。另外如果是新手推荐多看看优秀的开源项目代码，能学到很多。像我等平凡之辈自己瞎捯饬也捯饬不出来啥，倒不如多学学人家高手是怎么写的，实际上对于大部分公司的业务代码，不需要什么奇淫技巧，反倒是把代码写得直白易懂易维护最重要。


难以维护的Python代码
--------------------------------------

::

    # python 没有 docstring 维护基本就靠命名了，对于复杂参数的类型没有注释看起来心累
    def isRankingBetter(self, customer,topranking):
        testranking = getRanking(customer)
        return testranking > topranking

    // java
    public boolean isRankingBetter(Customer customer, int topranking) {
        int testranking = getRanking(customer);
        return testranking > topranking;
    }

上面是一段java和python的对比，用来说明为什么python难以维护。java版本一眼就能看出来传入参数的类型和返回值，但是遗憾的是python看不出来，在python中基本只有通过docstring你才能知道传入参数的类型。当项目大了以后，维护一份没有文档和注释的python项目基本就是灾难。笔者曾很喜欢python语言，认为python是“伪代码”语，表达能力强，但是有了维护python旧代码的经验后，我开始怀疑python是不是适合构建大型项目(python写多了以后反而越来越不喜欢动态语言)。

当然很多知名应用是python构建的，我觉得老外们软件工程做得还是不错的，把控好代码质量和单元测试（比如Quora创始人曾经解释过他们为什么选择了python,他们不喜欢java的冗长繁琐，C#被微软束缚，facebook因为历史遗留问题使用php并不意味着php是个好选择,Quora最后选择python并通过严格的单元测试控制质量）。但是我经历的一些使用python的项目工程方面却比较糟糕，代码维护起来非常吃力，开始让我对python产生严重怀疑。

java虽然写起来繁琐，但是不容易出错，动态语言写起来爽，但是维护和重构起来吃力，并且容易出错(写稍微大型的项目时要充分认识到这个问题)。我个人感觉就是使用动态语言要严格把控代码质量和文档，强制用pylint对代码静态检测，否则项目大了难以维护，python或许更适合有代码洁癖的人写，比较严肃的大型工程还是推荐java。踩过这些坑之后，希望你以后写python工程的时候注重代码的docstring，易读性，接口易用性，正确性等，不然写着爽后来也是要付出很大的维护代价的，实现功能仅仅是代码项目中的一小环。

重视细节
--------------------------------------

版式与布局
--------------------------------------

良好的代码排版可以让人理解代码更容易，格式化的基本原理是用直观的布局显示程序的逻辑结构。一点经验:

- 尽量遵守pep8，除了行长度可以适当放宽，比如django使用120列，我个人比较推崇120列，80列的时候经常超限制，比较浪费心思分行。短行在 web 显示，分屏，diff，code revew或者打印出来的时候都非常容易查看，所以不要写特别长的行。
- 合理使用"换行"使代码更易理解，同时更美观
- 合理使用"空行"和"括号"对代码块逻辑进行分隔，使层次清晰。

::

    # 分行之前，我见过最长的得俩屏幕连起来才能看完
    daily_report_data = db.session.query(Data.event_date, func.sum(Data.revenue).label('revenue'), func.sum(Data.payout).label('payout')).filter(Data.tag != Data.TagEnum.arbitrage).filter(Data.event_date < self._next_month_date).filter(Data.event_date >= self._this_month_date).filter(Data.finance_type == Data.TypeEnum.normal).group_by(Data.event_date).all()

    # 分行之后
    daily_report_data = db.session.query(
        Data.event_date,
        func.sum(Data.revenue).label('revenue'),
        func.sum(Data.payout).label('payout')
    ).filter(
        Data.tag != Data.TagEnum.arbitrage
    ).filter(
        Data.event_date < self._next_month_date
    ).filter(
        Data.event_date >= self._this_month_date
    ).filter(
        Data.finance_type == Data.TypeEnum.normal
    ).group_by(
        Data.event_date
    ).all()

    # 不好的分行
    employee_hours = (schedule.earliest_hour for employee in
                      self.public_employees for schedule in
                      employee.schedules)
    return min(h for h in employee_hours if h is not None)

    # 更具有可读性的分行，分行方式巧妙影响着代码可读性
    employee_hours = (
        schedule.earliest_hour
        for employee in self.public_employees
        for schedule in employee.schedules
    )
    return min(
        hour
        for hour in employee_hours
        if hour is not None
    )


你看看大概各需要几秒才能分别理解上边的代码，分行之后能在三秒之内大致理解代码是干啥的，但是太长行你光移动编辑器指针就要花几秒。所以有时候排版还是很重要的(想象一下每天盯着写成一坨和排版优美的代码分别是什么感受)，为了快速理解代码你要用上各种手段，尽量让代码更直观。当然有时候你拿不定注意怎么样选择的时候，就以一种最容易理解的方式写，下边是笔者常用的一些分行方式，有利于写出遵守pep8的代码:

::

    long_list_list_defition = [
        'a_long_variable_name',
        'b_long_variable_name',
        'c_long_variable_name',
    ]   # 这样定义的好处就是你可以非常方便的增添元素而不用修改定义结构

    from some_module import (
        a_long_variable_name, b_long_variable_name, c_long_variable_name,
        d_long_variable_name
    )

    if a_long_variable_name and b_long_variable_name and c_variable_name \
            and d_variable:
        # 我更倾向于用括号而不是反斜线来分行
        pass


    if (a_long_variable_name and b_long_variable_name
            and c_long_variable_name and d_long_variable_name):

        pass


    a_long_list_comprehension = [person.name
                                 for person in db.session.query(Person.name)]


    a_long_dict_comprehension = {
        person.id: person.name
        for person in db.session.query(Person.name, Person.id)
    }


    employee_id_list = [
        ins.id for ins in Employee.get_role_team_members(
            role_int, team_int, ['id']
        )
    ]


    def long_variable_function_name_and_function_params(a_long_variable_name,
                                                        b_long_variable_name,
                                                        c_long_variable_name,
                                                        d_long_variable_name):
        pass



    def long_variable_function_name_and_function_params(
        a_long_variable_name,
        b_long_variable_name,
        c_long_variable_name,
        d_long_variable_name
    ):
        pass


    return {
        'code': ErrorCode.OPERATOR_FAILED_NEED_TOKEN,
        'msg': ErrorCode.OPERATOR_FAILED_NEED_TOKEN_MSG,
        'data': {}
    }, status_codes.unauthorized


    new_employee = Employee.get_by_id(new_employee_id)
    (
        changed_advertiser_ids,
        changed_account_ids
    ) = assign_employee_advertiser_and_account(employee, new_employee)


    result = a_very_very_very_very_very_very_very_very_long_function_name(
        a_long_variable_name, b_long_variable_name,
        c_long_variable_name, d_long_variable_name
    )


命名
--------------------------------------

首先你要遵守pep8的规定，使用惯用法来命名。或者根据你们公司的python编码规范（如果你们公司有的话）

- joined_lower for functions, methods, attributes
- ALL_CAPS for constants
- StudlyCaps for classes

另外注意动态语言因为没有类型声明，所以在阅读源代码的时候，如果名称起的不好，很难推测出代码中间变量的数据结构，给阅读代码带来障碍(用同事的话说就是，python维护基本就靠命名了，《代码大全》等书甚至用了数章来说明命名的艺术)。比如一个字典列表，或者嵌套字典等，笔者维护过python代码，深感其中坑太多。我个人的经验就是适度在命名中加入一些类型提示，比如使用nums, cnts等作为后缀很容易知道是数值类型，数据库类都会用Model作为后缀，复数单词或者some_list等很容易知道是序列，some_mapper或者some_dict, some_set等基本从命名就知道什么数据类型了。当然这只是我的经验，有些人会反对这种命名方式，老实说如果代码写得是自解释的，可以不用这么来，但是我个人感觉这种方式虽然冗余，但是确实给我维护和阅读代码带来了便利。

python3中加入了type hint特性，所以我觉得类型声明对于维护代码来说还是非常便利的。但是注意，动态语言有鸭子类型的概念，所以有时候名称中的类型提示并不代表就是该类型，很可能造成歧义，这也是很多人反对在python中使用类似匈牙利命名法的原因。老实说我不怎么使用鸭子类型(虽然天然支持泛型)，我感觉鸭子类型是很多错误的来源(比如很多instanceof判断增加函数复杂度)，python3加上类型注解了，甚至mypy都加上类型检测了（python3中的注解只是为IDE工具提供便利，并没有真正的类型检查），说明类型提示对大型代码项目维护还是很重要的。我觉得对于软件工程重视不够的团队最好不要使用动态语言开发后台，写不好的话坑会很多，后期新人上手和维护成本很高，虽然python易上手，但想要写好工程代码，还是需要一定功底的。

- 注意词性。比如过程用动宾结构，用返回值的描述命名函数，数据变量使用名词，布尔数据经常使用is等作为前缀，数字类型使用cnt等作为后缀。
- 适当使用"匈牙利"命名法(能从命名推断类型)。比如一个变量明显是字典或者集合，加上后缀可能会更易理解，我个人是强烈建议通过前缀或者后缀增强名称的含义和类型（个人经验，有争议，不过我确实感觉这种代码更容易阅读理解，否则看一个变量看不出类型维护起来超级痛苦）
- 含义精确，具体胜于抽象。不要频繁使用诸如data，info，result，handle，process等概念太广泛的词汇给变量命名，不要使用偏门的简写，为了代码可读性冗余一些都可以(实际上对于现代语言长命名有一定好处，能减少冲突，容易 grep)。模棱两可的命名往往代表着某种警告（比如内聚不合理，不是单一职责等）。命名要能凸显出右侧表达式结果的类型和含义。
- 给函数命名的一个好办法：首先考虑应该给这个函数写上一句怎样的注释，然后想办法将注释变成函数名称。（来自《重构》）
- 术语表和命名规范。其实项目如果能建立术语表比较好，要不每个项目都用不同的词语命名比较混乱。命名会直接影响对代码语义的理解，还是要非常重视的。（比如不同项目用同一个名字表示不同含义，不同的名字又表示同一个含义，协作的时候非常容易混淆）

(注意这几个词语：『函数function』指有返回值的函数，『过程procedure』指无返回值的函数，『方法method』指的是类中的函数)

注释与docstring
--------------------------------------

.. code-block:: python

    def function_with_types_in_docstring(param1, param2):
    """Example function with types documented in the docstring.

    `PEP 484`_ type annotations are supported. If attribute, parameter, and
    return types are annotated according to `PEP 484`_, they do not need to be
    included in the docstring:

    Args:
        param1 (int): The first parameter.
        param2 (str): The second parameter.

    Returns:
        bool: The return value. True for success, False otherwise.

    .. _PEP 484:
        https://www.python.org/dev/peps/pep-0484/

    """

这个是google的docstring示例,是我比较推崇的一种格式。还是那个问题，动态语言没有类型声明，所以复杂函数要在docstring里写清楚传入参数和返回值的描述和类型。良好的docstring能让维护代码的人一眼就看明白这个函数是怎么使用的，即使内部很复杂，也尽量保持接口简单，容易使用。经常有人传出个嵌套字典（dict的key是主键，每个key对应的value里还有字典），这种相对复杂的数据结构还不注释，每次看这种函数都要打断点看返回结构。这种就是典型的接口易用性差，只在意实现功能，完全不管别人使用，合作起来比较心累。

- Docstrings = How to use code。代码约定
- Comments = Why & how code works

Docstring应该包括什么?接口易用性

- 意图(目的)。解释为什么需要它？有些对你来说很明显的东西对其他人来说不一定很明显。最好能用一句话描述意图和功能，简单明了。笔者在接手项目看代码的时候，很多时候知道代码做了啥，但是却不知道为啥需要以及在哪些地方会需要这些代码？
- 描述参数，返回值和会抛出的异常。我举个简单的例子， `def f(date): pass` ，仅仅看date这个参数你不知道传入str还是datetime.date，如果传入字符串又有很多格式的字符串，需要哪种格式？所以这个时候一个简单的描述 `date (str): 'YYYY-MM-DD'` 就能让使用函数的人一下子明白了。当然如果有单元测试实际上测试代码也是很好的文档，我们通过单元测试就知道怎么传值。另外使用了 `**kwargs` 如果都不说明就太不厚道了。对于传入的复杂的数据类型，最好注释下，否则看代码会非常蒙逼
- 使用注意事项。复杂的使用可以有demo示例说明。
- 需求文档，使用的api或者github, stackoverflow等链接。比如有个很trick的实现是你查阅 stackoverflow解决的，可以附上地址帮助阅读代码的人找到出处。对如复杂的需求实现，附上需求文档也会帮助他人理解。使用了第三方或者自己造的api，附上地址可以让新人快速上手了解。这些都是一些小细节，但是却可以给自己和维护代码的人带来巨大的便利。
- 大家都很懒，但是还是尽可能用极其简洁明了的话给所有的模块、类和函数来几句描述（为什么需要这个模块、类、函数？这个模块、类会在在哪里被使用？它完成了什么功能）？如果能很简单描述出来，说明代码功能明确，写得至少不算烂^_^。无法简单描述的话说明代码可能需要拆分。另外涉及到业务的代码一般还需要链接一下业务文档帮助后人理解和上手。

注释分5类（来自《代码大全》），但是仅『总结性注释』和『意图注释』可以接受

- 代码的重复:用不同的词语重申代码的内容
- 代码的解释: 解释复杂的有效的和灵敏的代码，通常有用但是尽可能修改代码使得代码本身更清晰
- 代码中标记： TODO 标记等，经验表明，往往写了 TODO 后来就一直成了 TODO，所以最好提交代码前把要做的 TODO 做完，TODO 仅仅作为一次代码合并之前的提示。TODO 注释记得加上姓名，日期，联系方式和提示，方便 grep。
- 代码中的总结：简化代码为一句或两句话，这种注释比重复代码更有价值，能帮助人快速理解代码
- 代码意图的描述：解释代码的目的。意图注释在问题一级上，而不是在答案一级，是一句利用答案的总结描述。『理解最初的编程意图是最难的问题』

注释怎么写?

- 当然，好代码 > 差代码+好注释，好的注释是很有价值的，坏注释不仅浪费时间还可能有害，自解释的代码最好。好的注释不是重复代码或解释它，而是使代码更清楚，注释在高于代码的抽象水平上解释代码要做什么事。
- 适当注释，仔细衡量，不要隐晦也不要多余。
- 及时更新。
- 注释代码中一些tricky的技巧或者特殊的业务逻辑，否则会让读代码的人摸不着头脑。
- 如果附上jira、bug、需求等的地址能够帮助理解代码，可以适当加上。
- 如果代码命名良好，结构合理，一般来说是不需要什么注释的。但是用一句话解释下意图和功能也是极好的，因为很多时候仅仅是想知道代码怎么用，读一句注释要比分析几十行代码快得多。
- 根据《代码大全》上注释的分类，仅『意图注释』和『总结注释』两类注释是可以接受的。

很多东西都需要自己斟酌，不要矫枉过正，比如说需要注释你就写一堆没必要的冗余的注释，说遵守pep8尽量不超过80列你连url都要拆成两行，我。。。。。。如果有些规范相冲突，你就以代码的可读性为标准，所有标准都是为了良好的代码设计的。我最怕和随意的程序员一起干活，随意就是写个函数print下就觉得正确了，没有docstring和注释，写的接口让别人难以使用。

公司项目毕竟不是自己过家家，我现在就是自己的小项目也会注重规范（自己维护起来也方便，不要相信你的记忆力）。很多用python的小公司就是很不规范，维护起来真心累。也希望所有看到这里的python学习者可以把规范重视起来(很多知名开源项目文档都相当不错)，这也是一个职业程序员应该具备的素养。毕竟大部分人不是造轮子的人，能把业务逻辑实现地简单优雅易维护也是一种能力。

* `《The Art of Readable Code》 <http://ningning.today/2017/07/22/%E8%BD%AF%E4%BB%B6%E5%B7%A5%E7%A8%8B/the-art-of-readable-code/>`_

异常处理
--------------------------------------
一般在我们的代码中会出现三种错误类型：

- 语法错误(Syntax Error): 比如手残打错了关键字等，可以通过编译器或者lint工具检查出来。动态语言要用好静态检测工具，防止代码上线了才发现直接跪了，修改成本高。（动态语言一大劣势）
- 逻辑错误(Logic Error): 逻辑错误一般是由于程序员的粗心或者需求理解不对导致的(比如该用+号用了-号)，也是一般bug产生的原因，可以通过单元测试等方式避免。
- 运行时错误(Runtime Error): 比如权限问题，文件不存在，网络请求失败等IO操作经常会抛出异常，这种错误需要程序员有意识进行处理，而不能假设操作一定就是成功的，尤其是涉及 IO 的地方。

之前没怎么写过工程代码的小盆友可能一开始会忽视对各种异常的处理，这里需要提醒的就是，工程代码如果想写得健壮就需要对程序中可能会出错或者抛出异常的地方进行异常捕获，捕获之后进行处理或者上抛给调用者(raise)。（防御式编程）


* `《google docstring示例》 <http://sphinxcontrib-napoleon.readthedocs.io/en/latest/example_google.html>`_

* `《注重细节:代码排版，命名与注释》 <http://ningning.today/2017/01/22/python/python-coding-details/>`_

安全
--------------------------------------
防范常见的xss，csrf，sql注入等攻击，不要信任来自外部的任何输入。对于外部接收的参数都要过滤，比如表单，对外的 api 等。对内的函数无需每一层都加上参数过滤（基于约定或者规范编程，没有遵守约定抛出的异常由调用者负责处理）。
有一个例外就是数据库查询的参数，最好经过一次参数校验，防止不合理参数造成慢查询等问题。或者简单一些就直接使用断言

小白的踩坑记录
=====================================================================

文档化
--------------------------------------
团队项目开发前的统一三要素：统一需求/开发文档，统一代码规范，统一环境（编译/测试/发布）。
很多程序员是懒得写文档的，仿佛牛逼的程序员不需要写。但是看人家真正牛逼的开源项目比如flask和tornado等，无论是代码还是文档都做得相当棒。对于一些项目，有些东西如部署步骤；常用命令等还是可以记录下来的，可以使用wiki或者readthedoc，gitbooks等文档工具记录一下，方便新人上手。如果不知道记录啥，就把你发现不止一次会用到的东西文档化。个人认为需求文档也应该有历史记录，方便接手的人可以快速了解业务和需求变更。数据库字段的含义也应该及时记录和更新。

Readme Driven Development:

- Explain the system's pupose. (What is the business reason ? Why are we here?)
- Describe the scope. (What defines what the system does and doesn't do?)
- Summarise what it does. (What does it actually do? What is it for?)

只有少数很复杂的系统需要详细的文档，架构图、UML、数据模型、处理流程、业务逻辑等需要整理成文档。Write the minimum viable system documentation.


代码分支与代码管理
--------------------------------------
做好代码分之管理，分清楚开发、特性、bugfix等代码分枝，不要在同一个分之上一下修改太多功能，导致修复问题不好定位。比如经常和同事做一个需求，结果一个人把几个需求堆到一个分之改了，把不该上的功能也给上了，这种小细节还是需要注意的，否则就会给测试、上线等带来严重麻烦。命名分之的时候注意使用有意义的命名，比如附带上task的号码，jira号等等，把分之和你要解决的问题关联起来。

注释
--------------------------------------
有经验的人都知道看别人的代码是一件很痛苦的事情，尤其是没有任何注释的代码。代码除了完成需求外，最重要的就是维护和协作，除非你觉得你做的项目活不过仨月(或你自己玩玩的项目随便你怎么艹)，否则就一定要重视代码质量，防止代码腐化(破窗)以至难以协作和维护。有时候比写注释更难的是知道何时写，写什么注释？python里有规范的docstring用来给类和函数进行注释，除了说明功能外，关于github,stackoverflow链接、复杂的传入传出参数（比如嵌套字典作为参数这种你都不注释就很不合适了)，类型说明、需求文档和bug的jira地址等都可以注释。凡是你回头看代码一眼看不出来干啥的，都应该有适当的注释，方便自己也方便别人。

当然，最重要的是代码清晰易读，好的命名和编写风格的代码往往是自解释的，看代码大致就可以看出功能。建议就是给所有的模块、类和函数都加上注释，除非一眼能看出来这个东西干啥，否则都应该简洁注释下，让别人不用一行行看你的代码就大概知道你这个东西是干啥的。最后注意的就是一旦函数更改及时更新注释。qiniu的sdk写得就不错，可以去github看看。总之，"Explicit is better than implicit.", 代码里不要有隐晦的东西，一时偷懒将来可能会付出几倍的维护代价，请对将来的自己和他人负责。

* `《python docstring》 <http://bwanamarko.alwaysdata.net/napoleon/format_exception.html>`_

Code Review(代码复查)
--------------------------------------
笔者认为code review是一件非常重要的事情，可以有效防止代码腐化，同时方便同事了解业务(可以说编码规范、静态分析、代码审查和单元测试是保证代码质量的几个重要工具，没有使用这几个工具之一将来代码都可能难以维护)。可以在公司搭建Phabricator（facebook在用）gitlab 类似工具进行代码review。可惜小公司流程不严格，codereview总是坚持不下去，要不就是被同事吐槽总是给他挑刺。实际上如果是新手能够从code review当中快速学到很多东西，比如编程惯用法，摆脱不良编码习惯，不良设计和难以维护的代码等。review的时候对事不对人，代码如果有明显缺陷快速记录个TODO等待review后修正，以一种开放和学习的心态看待review，慢慢整个团队的实力和代码质量就会提高。review就是个互相学习进步的过程，正规的团队都应该严格遵守，而不只是走走流程。

- 建立 review 检查表，防止不合理、过于复杂、明显缺陷、可读性差的代码。眼睛足够多，bug 无处藏。
- 建立提交模板，每个提交是需求、bugfix还是啥一目了然，同时贴上需求、jira 等地址，方便追溯。
- 对事不对人，review 和被 review 的人都要以一种开放和学习的良好心态看待 review，共同进步。新手或者新加入项目的人不要过度吹毛求疵(会有很大心理负担和反感情绪)，共事久了步调和代码风格慢慢趋同了。
- 及时复查，防止一次太多的commit。
- 检查内容：
    - 代码规范（风格和命名等，动态语言没类型声明，很依赖良好的命名推断变量含义和类型）。同志们学好英语，命名真不是个简单的问题(尤其是各种中式英文和缩写)。
    - 是否有单测
    - 是否健壮（安全性、性能、异常捕获）
    - 必要的文档和注释（意图，外部链接需要注上）
    - 可读性和可维护性(是否有过于复杂的逻辑)
    - commit 信息（commit信息是否准确，比如附上 jira 或者需求文档地址，bug 地址等，有迹可循, 目前团队加上了提交模板，对于 bug fix、新特性、重构等都需要填写对应的模板信息）
    - 代码洁癖要适度，不要吹毛求疵。review 过程中出现分歧是很常见的，每个人都有自己的编码习惯。如果出现难以解决的分歧，可以列出优劣表格，对各自的方式有一个量化的分析。如果无伤大雅，不必吹毛求疵。

* `《https://www.kevinlondon.com/2015/05/05/code-review-best-practices.html》 <https://www.kevinlondon.com/2015/05/05/code-review-best-practices.html>`_
* `《如何用人类的方式进行 Code Review》 <https://zhuanlan.zhihu.com/p/31581735>`_


日志与异常记录
--------------------------------------
一定要有良好的日志记录习惯。良好的日志对于记录问题至关重要。python有方便的日志模块帮助我们记录，日志输出的代价是比较小的，python的日志模块尽量做到对函数功能没有性能影响，可以在线上和开发环境设置不同的log等级，方便开发调试。注意别再日志语句里引入了bug或异常。有时候需要判断什么时候需要日志，记录哪些东西方便我们排查问题，分析数据。
对于异常，一定『不要吞掉任何异常』，常有新手上来就try/except，也不区分非退出异常，也没有日志记录(坑啊......)。请先阅读python文档的异常机制，可以使用Sentry等工具记录异常。同时发生异常时候的时间，调用点，栈调用信息，locals()变量等要注意记录，给排查错误带来便利。有些错误的复现是比较困难的，这时候日志和异常的作用就凸显出来了。

* `《每个 Python 程序员都要知道的日志实践》 <http://mp.weixin.qq.com/s?__biz=MzA4MjEyNTA5Mw==&mid=2652564362&idx=1&sn=f33910af004f276bbef7ae52e0757bcb&chksm=8464c3c0b3134ad617bcffd865894344367fdd2995a0d5ff9c4da30e0c158b3d02b3d616f615&mpshare=1&scene=23&srcid=1124K7Ht1FP2A1Fnvi3HTBE5#rd>`_
* `《日志的艺术（The art of logging）》 <http://www.cnblogs.com/xybaby/p/7954610.html>`_

调试
--------------------------------------
调试也是个很重要的问题，不可能保证代码没bug，要命的是有时候写代码完成功能的时间还没调试的时间多。注意复现是排错的第一步，之后通过各种方式确定原因（访问日志、邮件报的异常记录）等，通过走查代码、断点调试（二分法等）确定错误位置，确定好错误原因了就好改了。修复后最好反思下问题的原因、类型等，哪些地方可以改进，争取下次不犯一样的错，慢慢减少错误才能越来越高效。

* `《调试九法》 <http://www.wklken.me/posts/2015/11/29/debugging-9-rules.html>`_

尽量写出对自己也对其他人负责的代码，上边费了牛劲都是在阐述这个显而易见但是没多少人严格遵守的东西。用动态语言写大型项目维护起来要稍麻烦，
很多新手写代码不注重可维护性，甚至自己写的代码回头自己看都一脸懵逼，问了一句这代码TM是干啥的？
一开始的负责会为以后协作和维护带来极大便利（当然你想干两天就走让其他人擦屁股就当我没说）。
最后，很多东西我也在摸索，上面的玩意你就当小白的踩坑记录，随着理解和经验的加深我会不定期更新本篇内容。另外我发现网上大部分是教程性的东西，对于python相关的工程性的东西很少，我很疑惑难道大部分公司的python项目都写得相当规范？没人吐槽？反正我是踩过坑，希望看到过本章的人能把python代码质量重视起来。

如何定位和修复 bug：复现和定位。定位需要找到 bug 出现时候的上下文信息，可以用 log，sentry 等查看。确认之后通过走查代码、断点调试等方式寻找代码逻辑错误。

- 第一步是复现，偶尔才复现的代码是很难排查错误的。如果不好复现但是有 sentry 之类的记录工具也是极好的，sentry 会记录当前栈信息和变量信息，非常有利于排错。
- 走查代码。使用 pylint 等静态检测工具排除低级错误(你应该把它集成到开发工具里)。
- 看日志，各种日志(logging, nginx)，看 sentry 异常信息
- 问同事，让同事帮忙 review 审查代码。有时候人有思维定势，你自己看不出来的别人可能一眼就看出来了。小黄鸭调试法
- 断点调试。看变量值。二分法排查代码位置，快速试错定位。比如一个地方很有隐秘的错误，但是又不好快速确定位置，我们就可以用二分加断点的方式快速定位到具体哪一块出了问题。
- 不要死磕，一个法子不行换一个。死磕可能会耗费太长时间并且容易进入死胡同，在一个大型复杂系统中定位 bug 原因是对技术、经验、毅力、灵感、心理素质的很大考验，休息一会可能就解决了。
- 极难排查和复现的 bug 可以无限期搁置。
- 找到 bug 修复以后增加相应单元测试用例，这样对回归测试非常有利，同时避免重复犯一样的错误。tricky 的地方要加上注释。
- 留心非代码因素：比如代码是否正确部署上线等(比如之前脑残查一个 bug 无解最后发现是部署到线上没成功，根本没起作用）。如果实在没发现代码级别错误，单测也比较完善，可能就要考虑下非代码因素。
- bug 总结：建立错误检查表(核对清单)，哪些可以避免的记录下来，防止以后再犯。(团队的知识财富)

  大多数 bug 都可以通过设计复审、代码审查、代码静态分析、测试等找出来，我们可以综合利用以上手段尽量减少代码缺陷。

重构与维护
--------------------------------------
不知道你有没有这种感觉，看那些知名代码库flask等，人家写的代码水平是比较高的，但是自己的项目确实一团糟。我觉得代码要经常去重构，想着怎么写更优雅，更容易理解和维护。我个人感觉好的代码就是不断修改出来的，实现一个需求的时候，适当想想怎么设计更加优雅易维护，编写代码的时候注意想着可读性。完成需求了如果代码可以设计更优雅，可以尝试重构下，慢慢代码水平就上来了。如果总是直来直去堆砌需求代码，业务逻辑写再多依然不会有进步(我个人感觉写python有时候反而会降低编程能力)。牛人和计算机高手很多，能写出良好的工程代码的人却很少(试想一下让你维护一个『牛人』的『精巧』代码)。代码一次编写，却可能被无数次查看、修改和维护，在可读性和可维护性上的努力长远来看是值得的，编写代码只是整个软件项目中很小的一部分。写代码的时候最好也从维护者的角度思考一下。
Code Quality: Simple, Well-tested, Bug free, Clear, Refactored, Documented, Extensible, Fast.

- 重构：在不改变代码功能的情况下优化代码设计。修改功能和优化代码不要同时做。优化应该以可读性为标准。
- 接手老项目的时候不要盲目大规模重构，但要保证代码仓库越来越『干净』，不要破罐子破摔。
- 可以通过设计(需求)归档、代码规范、静态检测工具、单元测试、必要的注释和文档、code review(代码复审)、重构、服务化等手段增加项目的可维护性。
- 动态语言的重构工具支持不够完善，重构的时候要注意别改坏了逻辑，要十分谨慎。

* `《重构 - 读书笔记(PYTHON示例)》 <http://www.wklken.me/posts/2017/06/17/refactoring-07.html>`_  来自 wklken's blog

Python 做业务后端的优缺点分析
--------------------------------------
笔者从实习开始做 Python 后端，经历过一些新项目、老项目，以及和很多 python 工程师(豆瓣、知乎)协作过，大概总结下 python 做 web 业务后端的优缺点吧，尽量客观，
总得来说就是用动态语言写项目在追求高生产力的同时要严格把控工程质量。先说优点:

- 多面手。python 可以写方便地写爬虫、网站、数据分析、运维脚本等，都有比较成熟的框架，目前比较火，TIOBE 里脚本语言排第一。
- 轮子多。python 发布时间比 java 还早，大量现成的轮子可以用。我觉得即使是 web 之王 php 做网站开发体验和效率上来说并不比 python 强。这可能也是 Instagram 和  Quora 等选择 Python 的原因。
- 表达能力强，语法糖多，生产力高。笔者喜欢动态语言的一个原因就是表达能力强，用更少代码完成功能。(代码行数越少意味着高生产力和低出错率，当然不一定对可读性有帮助)

缺陷:

- 解释性语言执行效率低，大部分时间用在 IO 密集场景，比如 web 后端。不过大部分公司不用担心性能问题，除非真到了一定用户量级。
- 开发工具支持不够完善，不如 java 有那么完善的 IDE，Pycharm 还不错，但是依然解决不了滥用动态特性导致的补全和跳转等问题
- 易编写，但难以重构和维护，易出错，工程上不够友好，较难写出 clean code(笔者基本上会强制上 pylint and autopep8, 模仿 gofmt 吧)。基本上重构只能依据字符串匹配，老实说每次重构有稍微大一些的改动都会有点担心
- 滥用动态特性导致代码不好维护。这是个双刃剑，但是对工程来说还是不要滥用。有时候会利用一些动态特性使用黑魔法来快速完成需求，但是工程上来说这是很不利于维护的。
- 没有类型声明，看不出一些复杂类型的数据结构（Python、php 都在不遗余力地加上 type hint），代码写糙了维护起来很累（看不出复杂变量的类型和结构，阅读代码吃力，我都是给复杂类型加上类型注释），命名和编码习惯很重要
- 缺少一些最佳实践（技术、小白文章偏多，工程实践文章比较少），以很多 python 的中小公司在软件工程上管理不够，无规范、无文档、无注释、无单测、无持续集成的尿性，还是慎用动态语言瞎胡搞，后期维护成本会很高。
- python2，3 不兼容，迁移有成本。我个人觉得 python 敢于抛弃当初的设计是值得赞赏的，但是很多企业并没有足够的资源来去迁移
- 招人不好招，这两年 python 雷声大，雨点小，而且基本都是在 AI 领域。有经验的 python 后端远没有 Java 好招(往往很多人学得还是半吊子写代码很随意，不重视工程质量)，更多是创业公司、中小公司使用


开发习惯
------------------------------------

- 认识和熟悉所在团队中的成员（笔者之前一直做得不够好，这一条远比想象中重要，内向性格有时候会比较吃亏），良好的沟通和协调能力能帮助你更快完成(或者委托)任务。
- 确保正确了解需求，确保熟悉所做的业务；需求分析；适当设计。流程图或者文档有时候可以帮助理清楚业务。比如知乎有 rfc 机制，每次做一个稍微大点的需求都需要写设计文档。
- 番茄工作法，劳逸结合(working smart rather than working hard)，一次只做一件事(do one thing and do it well)。长时间专注写代码是非常消耗精力的。确保编码期间足够专注。快速迭代。
- 边写边测，增量式编程。虽没有使用 TDD 开发的习惯，但是对于稍复杂的逻辑就要写单测，以便及时发现错误，越早发现越容易修复(修复成本随时间指数增加)。我习惯用文件变动监控工具(when-changed fswatch等)检测文件变动，每次保存文件自动跑相关测试(比如 nose pytest 等都可以执行单个文件或类的测试,你可以快速验证当前代码是否有问题，及时修改或者重构)。TDD 的好处之一就是改善设计，自顶向下考虑，笔者有时候也会尝试用 TDD。
- 注释先行，意图导向，表达明确，牢记可读性可维护性，可追溯（附上需求文档地址，方便维护者查看）。写一个模块、类或者函数之前先想好它的功能，按照功能命名，之后写简单的注释描述其意图和功能，通常不超过三句话，虽然大部分时间只有一句话(只做一件事) ，但是能快速让后来的维护者了解你的意图。别看人代码最头疼的就是看不出代码究竟是要干啥。
- 文档驱动编程(Document Driven Development):比如写一个脚本的时候，应该在文件头部注明需求地址 url(保证代码功能、意图等是可追溯的)，写下实现方式和目的等。有时候对于很复杂的业务逻辑笔者会用自然语言描述步骤，之后再用代码实现。对于需要经常维护的代码，必要的文档是值得的。
- 边开发，边重构，及时清理技术债。如果有代码写糙了（圈复杂度太高、可读性差、代码重复等坏味道），应该及时重构不好的代码，这时的重构成本是最小的。代码写得复杂到自己都快看不懂了是个危险的信号。
- 善用工具。比如笔者使用的 vim 插件 python-mode 集成了 pylint、pep8、pyflakes、autopep8、isort 等工具，方便快速检测代码是否有语法错误和规范问题。每次保存文件后我都会在 vim 里执行一遍 pylint 和 pep8 检测，确保代码在规范上没问题。
  (即便如此动态语言依旧很容易犯错，比如使用了未定义的属性，参数个数不一致等开发工具都不会报错，但是一上线就报了异常，所以动态语言编码还是需要很谨慎，同时通过良好的编码习惯、测试和 code review 来消除缺陷，有些同事说用动态语言
  写大型项目会睡不好觉，不无道理。目前笔者所在的小团队就在 CI 上加了 flake8，pylint 检测，代码写糙了过不了，同时所有同事提交之前用 autopep8 格式化代码，用 isort 整理导入包顺序，避免了风格不统一的问题)
- 重视规范。代码量上去以后没有规范就是噩梦，也是很多小公司代码不忍直视的原因。(无文档、无注释、无单测、风格混乱、难以维护)
- 追根溯源。在代码、提交信息、文档中记录需求文档地址、引用地址等。方便维护者能够根据代码提交寻找代码意图，尤其是几乎没有任何文档注释的代码。让人上来就看一段不知所云的代码无比痛苦。写代码有时候和写文章、论文差不多，可以在 docstring 里附上相关链接。commit 信息都应该足够重视，不要瞎写，要能体现代码提交意图（修复 bug、新 feature、代码优化等）
- 结对编程。结对编程和TDD是极限编程中大力提倡的，国内似乎没有多少公司在实践，一般帮助新人了解项目或者带实习生的时候，结对能帮助新人快速上手。

平常可以留心下周围优秀的同事都有哪些好习惯，我们可以学习并改善下自己的开发流程。

- 12 Schedule Time to Lower Technical Debt
- 11 Favor Hign Cohesion(low cyclomatic complexity)
- 10 Favor Losse Coupling
- 9 Program with Intention(Simple Design: Passes the tests; Revieals intention; No duplication; Fewest elements)
- 8 Avoid Primitive Obsession(Imperative code is packed with accidental complexity)
- 7 Prefer Clear Code over Clever Code
- 6 Apply Zinsser's Principle on Writing(Simplicity;Clarity;Brevity;Humanity)
- 5 Comment Why, not What
- 4 Avoid Long Methods--Apply SLAP (long is not about length of code, but levels of abstraction)
- 3 Give Good Meaningful Names (if we can't name it appropriately, it may be a sign we've not yet understood its true purpose)
- 2 To Tactical Code Reviews
- 1 Reduce State & State Mutation

Think more, type less. Aim for minimalism, fewer states, less mutability, and just enough code for the known, relevant parts of the problem.


《The Zen of Python》 - Tim Peters

::

    Beautiful is better than ugly.
    Explicit is better than implicit.
    Simple is better than complex.
    Complex is better than complicated.
    Flat is better than nested.
    Sparse is better than dense.
    Readability counts.
    Special cases aren't special enough to break the rules.
    Although practicality beats purity.
    Errors should never pass silently.
    Unless explicitly silenced.
    In the face of ambiguity, refuse the temptation to guess.
    There should be one-- and preferably only one --obvious way to do it.
    Although that way may not be obvious at first unless you're Dutch.
    Now is better than never.
    Although never is often better than *right* now.
    If the implementation is hard to explain, it's a bad idea.
    If the implementation is easy to explain, it may be a good idea.
    Namespaces are one honking great idea -- let's do more of those!
