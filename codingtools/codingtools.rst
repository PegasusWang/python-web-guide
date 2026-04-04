.. _codingtools:

开发和编程工具
=====================================================================

..

  Do one thing, and do it well. - A principle of Unix philosopy

工欲善其事，必先利其器 开(装)发(逼)工具
--------------------------------------------------

- Pycharm/IDEA/Goland(JB全家桶)。专业的python IDE，功能很强大，特别喜欢它的代码merge工具，不想被编辑器折腾死的推荐直接使用，五星级推荐。(除了内存占用大点)。如果你不喜欢折腾编辑器，请直接用 IDE，经常看见一些用裸编辑器写代码的，代码规范检测都没有。
- Neovim/vim/Emacs/Vscode/Sublime/Atom: 跨平台的编辑器。vim 目前是笔者的最爱，你可以在慕课网和 B站搜索到我的视频教程
- meld/vimdiff/kdiff3: 跨平台的文件对比和冲突合并工具。当然还有付费的 BeyondCompare，对笔者来说大部分场景 vimdiff 就很好用
- devdocs.io: 文档查询工具，可以在线查询
- EditorConfig: http://editorconfig.org/ 用来统一编辑器配置。如果成员用不同的操作系统和编辑器，建议使用。尤其是对于 python 这种使用缩进的语言

一定要有个趁手的开发工具(它甚至比你女朋友都重要)，不管是IDE还是编辑器，你程序员生涯的小半辈子都在和它打交道(提升编辑效率的秘诀在于多用键盘快捷键，少用鼠标，以及可以高度定制、和扩展功能的编辑器)。甚至编程字体你都要谨慎选取，比如字体可以很好区分'1', 'l', 'I', '0', 'O', 'S', '5'等易混淆字符，给浏览代码带来便利。如果使用的是mac可以google下 "Mac OS X development environment setup"，有惊喜呦。最后注意你用编辑器的话一定要用 pylint，pep8 检测插件，否则不遵守规范可能会导致用 IDE 打开项目后一堆警告(别人会想问候你祖宗的)。
更多 mac 工具可以参考：https://github.com/jaywcjlove/awesome-mac 。搜 awesome-python 或者 awesome-flask 等有很多类似项目。

一些提升效率的建议：

- 指法用对，练习盲打，提升敲击数字键的成功率
- 熟悉你的开发工具，各种 IDE 或者编辑器快捷键。vim 等高度定制的编辑器允许你按照自己的习惯修改快捷键
- 学习一门脚本语言（编写自动化脚本），编写你的命令行工具（一个可执行的 python 文件放到 bin 下就是一个命令行工具)
- 多用键盘快捷键少用鼠标。修改系统键盘按键，比如 capslock 使用频率比较低，一般我改成了 ctrl 键，因为用开发工具频繁使用到 ctrl，改成 ctrl 之后效率提高不少，小指头也不疼啦。
- 自动化（比如监听文件变动刷新浏览器、重启http服务等）
- 用好终端和命令行工具（我建议后端/运维等用 mac 或者 linux 系统，因为 server 大多跑的 linux，熟悉命令行会给你调试和面试带来便利）

* `《使用vim+tmux+zsh+autojump高效工作》 <http://ningning.today/2016/11/09/tools/vim-tmux-zsh-autojump/>`_
* `《玩转 vim 与 Terminal (视频)》 <https://zhuanlan.zhihu.com/vim-video>`_
* `《Mac 无鼠标编程指南（视频)》 <https://zhuanlan.zhihu.com/p/91031876>`_


MacOS 开发效率工具
--------------------------------------------------
- Item2: 替代原生的终端。https://medium.com/@RyanDavidson/make-your-terminal-more-colourful-and-productive-with-iterm2-and-zsh-11b91607b98c
- Alfred: mac 下一款功能强大的工具，不过我一般只用它快速打开软件(比如直接输入app名前缀快速切换不同app)。可以用 python 编写一些自己的 workflow 提高效率(https://github.com/deanishe/alfred-workflow)，比如把时间戳转成日期等。 https://github.com/derimagia/awesome-alfred-workflows
- Dash: 强悍的文档查询工具。支持非常多编程语言和框架。windows 和 linux 可以用 Zeal。或者 https://devdocs.io/
- CheatSheet: https://www.mediaatelier.com/CheatSheet/ 显示 mac 快捷键
- mac-setup: https://github.com/sb2nov/mac-setup mac 下各种编程语言开发环境配置指引
- Hammerspoon: 开源的mac窗口管理工具 https://github.com/Hammerspoon/hammerspoon
- Magnet/chunkwm/Amethyst/yabai 窗口管理辅助工具，拖拽窗口到屏幕边缘可以自动半屏， 全屏或者四分之一屏幕，还可以设定快捷键完成分屏，现在已经离不开magnet 分屏了。
- Tiles: 类似 magnet 窗口管理软件，免费！ https://freemacsoft.net/tiles/
- Karabiner-Elements(mac): 改键工具 https://github.com/tekezo/Karabiner-Elements 也可以用来禁用内置键盘(mac自带修改capslock为 control)
- Be Focused: mac 下番茄工作法工具，可以用来给任务计时，或者提醒该休息下了
- Qbserve: https://qotoqot.com/qbserve/ 一个 mac 下的时间追踪软件，可以查看自己在不同软件耗时，改善时间和工作管理
- xbar: 一款可以在 macos 菜单栏显示任意信息的 App，可以通过脚本扩展功能。有插件商店
- vimac/homerow: 用 vim 的方式操作 mac，彻底抛弃鼠标提升效率！新款叫做 homerow。 https://github.com/dexterleng/vimac

网址 https://gist.github.com/lornajane/3892c39098cf70baa9c7a1874cddf233  列举了使用纯键盘操作 mac 的建议和所用软件

Mac微信工具
--------------------------------------
- 微信小助手：https://github.com/MustangYM/WeChatExtension-ForMac  支持微信多开、消息防撤回、微信皮肤等多种功能

命令行工具
--------------------------------------
- tmux/tmuxp。比screen好用，可以用来分屏，托管进程等，服务器端必备神器，ubuntu下基本就不用使用terminator之类的分屏工具了。最近看youtube视频还发现有人在服务器上使用tmux和vim结对编程，两个人同时attach到一个session里，基情四射。
- vim。本人比较喜欢的编辑器，平常写代码、博客、文档等使用频繁，配上各种插件编辑效率很高。http://vimawesome.com/ 可以到这个上面安装排名靠前的那些插件，能够大大提高编辑效率，部分替代IDE(本人装了六七十个插件，满足各种变态的编辑需求)。其他优秀的编辑器sublime，atom，vscode，emacs等根据个人喜好来吧，不过vim等终端友好的编辑器方便在服务器上直接写代码，和本地体验一样，缺点就是补全和跳转支持不完善，对新人不友好，也可以 Pycharm  和 vim插件配合。(在google搜索python awesome等可以在github上搜索到一些awesome项目，总结了该语言很多技术工具)。网上还有很多牛人开源了自己的 dotfiles，我们可以参考下别人的 vimrc 配置。
- neovim: 新时代的 vim，我在这个配置(https://github.com/PegasusWang/vim-config)上自定义了自己的配置，使用起来性能和反应速度上远超原生的老古董 vim，目前笔者已经全面迁移到 neovim，用着很爽。感兴趣可以关注笔者知乎专栏，我录了一些针对初学者的教学视频。插件搜索：https://neovimcraft.com/
- vim-bootstrap: 一个快速建立不同编程语言 vimrc 的创建工具 https://github.com/editor-bootstrap/vim-bootstrap
- ranger: 用 vim 的方式管理文件，替代 mac 下难用的 finder。
- oni: https://github.com/onivim/oni/ 构建在 neovim 上的 IDE。还有 VimR 等项目。
- wemux: tmux 共享，https://github.com/zolrath/wemux
- sshfs: 本地挂在服务器文件夹
- tmate: https://tmate.io 终端共享工具，结对编程。很多现代化编辑器 vscode, atom 提供结对编程的插件。
- asciinema: 终端会话记录工具。https://asciinema.org/ 可以用来录制终端演示操作，而不用录屏。
- oh-my-zsh。替代原生的bash shell，提供了好多方便的特性和漂亮主题，支持插件比如 zsh autocomplete。linux/mac下vim+tmux+zsh简直是绝配，甚至可以直接在服务器上方便地撸代码，跟本地开发体验没区别。
- brew(mac)。类似ubuntu下的apt-get，可以方便安转各种软件和工具。
- autojump。方便在命令行里来回跳转目录。
- tldr: 列举出常见命令行工具用法。linux 命令行很多参数又不好记，man 手册比较难用，可以用这个 tldr 替代。https://github.com/tldr-pages/tldr
- rmtrash/safe-rm: linux 自带的 rm 非常危险，可以使用安全删除工具先放到垃圾桶。`saferm  <https://zhuanlan.zhihu.com/p/91515325>`_
- when-changed: 一个可以监控文件变动并且自动执行命令的工具，写脚本代码观察编写边输出结果的时候比较方便。笔者很多视频演示过
- https://github.com/onceupon/Bash-Oneliner
- epy-reader: https://github.com/wustho/epy 一个在终端下阅读 epub 电子书的工具，用快捷键 "o" 还可以打开图片
- 现代 unix 工具：https://github.com/ibraheemdev/modern-unix
- fanyi: 命令行版本的翻译工具 https://github.com/afc163/fanyi
- cheat.sh: 程序员小抄工具，可以快速查询各种命令、语法等用法 https://github.com/chubin/cheat.sh
- mackup: mac 备份软件配置  https://github.com/lra/mackup 
- edex-ui: 一个炫酷的终端模拟工具 https://github.com/GitSquared/edex-ui

Mac 终端快速配置
--------------------------------------
- 安装iterm2 替代难看的原生终端
- 安装 home brew 方便装各种工具
- 安装 oh-my-zsh or fish
- 安装 oh-my-zsh 主题 powerlevel9k 或者 spaceship。推荐使用异步的更快的 https://github.com/romkatv/powerlevel10k。 常见其他主题有(pure, powerlevel9k, spaceship)
- 安装 vim / spacevim /neovim
- 最好安装 tmux 用来替代iterm2 分屏
- 按需安装 htop/btop/autojump/z/fzf/ag 等命令行工具(使用 brew 可以安装)

可以参考我 github 上的快速配置教程：

- https://github.com/PegasusWang/linux_config/tree/master/mac 笔者的 MacOS 终端快速配置
- https://github.com/bhilburn/powerlevel9k/wiki/Show-Off-Your-Config

打字速度练习
--------------------------------------
虽然程序员不是打字员，但是对笔者来说，需要记录大量文档和阅读笔记，高效的键盘和打字速度可以大幅增加(我使用 HHKB键盘+Vim编辑器无鼠标编程)码字效率。
打字速度上去以后(一开始正确率比速度重要，如果不是刻意练习正确率打字再多效果也不明显)，你可能会更加喜欢记录文档和笔记了，脑子里的想法可以快速用键盘来实现出来。
编程和平常打字不同的一大区别就是需要经常使用各种特殊的符号，如果没有经过刻意练习会经常打错符号。

- https://www.ratatype.com/typing-test/  先来做一个 wpm 测试吧
- https://typing.io/  包含代码片段的练习网站
- https://www.keybr.com/ 可以根据英文『音节』来练习，提升因为打字速度和正确率
- http://www.speedcoder.net/  可以展示出来正确的指法
- https://www.typing-lessons.org/ 一套系列的打字和指法教程，没事的时候可以练习一下，摆脱二指禅打字。笔者目前就练习这个
- https://www.keyhero.com/wpm-typing-tips/ 同样一个针对程序员的打字练习网站。笔者没事就会练习一下
- gtypist (brew install gnu-typist; gtypist) 一个linux/MacOS 命令行打字练习工具
- https://kaiyiwing.gitee.io/qwerty-learner/ 既可以练习打字，又能学习单词，提供了四六级和雅思托福等词库。还有编程语言 API 词库

Mac 屏保软件
--------------------------------------
- https://github.com/JohnCoates/Aerial
- https://github.com/packagesdev/savehollywood

Git 相关
--------------------------------------
- gitx(mac):方便查看代码提交历史，便于了解整个代码仓库是怎样一步步构建的。http://gitx.frim.nl/user_manual.html
- tig: text-mode interface for git. 喜欢命令行的可以尝试下，比如可以在终端下浏览提交记录和文件修改。 https://github.com/jonas/tig
- git-extras: 提供了很多方便的 git 命令行工具，比如 git summary 可以输出代码的提交统计。https://github.com/tj/git-extras
- diff-so-fancy: 让命令行下使用 gitdiff 更加可读 https://github.com/so-fancy/diff-so-fancy
- git-cz: https://github.com/commitizen/cz-cli 用来统一 git commmit 提交信息，代替 gitmessage。参考文章：https://juejin.im/post/5afc5242f265da0b7f44bee4
- pre-commit: git pre commit 工具，比如可以在 commit 之前增加代码静态检查或者运行单元测试。 https://pre-commit.com/
- gitignore.io: 搜索ignore文件模板，有常见编程语言的示例模板。https://www.gitignore.io
- lazygit/gitui: 终端 git UI 工具


Chrome 开发者插件
--------------------------------------
- FE前端助手(FeHelper插件)：浏览器前端插件，Json 格式化/json比对/代码美化/编解码/二维码等很多有用的工具，强烈建议安装
- SurfingKeys/vimium/Cvim: chrome 插件，可以用 vim 的方式操作浏览器，很方便，不用鼠标也能完成大部分操作，笔者使用的SurfingKeys比较强大，可以用 ctrl+i 来用 vim 编辑输入
- wasavi: 想在网页编辑框使用 vim 可以试试这个插件。安装完之后使用 ctrl+enter 就可以了 https://github.com/akahuku/wasavi
- Octotree: Chrome github 浏览插件，可以把 github 项目的目录树结构展示出来，非常方便
- Github Hovercard: 可以在浏览 github 的时候展示一些链接信息，比如可以查看作者的个人页
- Momentum: 美化 Chrome 界面的插件，有很多漂亮的图片作为背景
- Onetab: 用来整合 chrome tab到一个页面，如果打开了太多窗口特别占用资源的时候可以使用
- LGTM: 有些开发过程中，需要一个同事review 代码后评价 LGTM(Looks Good To Me)才能 merge 代码，这里是图片版的 LGTM
- SimpRead: 简悦，阅读模式 chrome 插件，支持导出和分享。试了一下导出知乎回答还不错
- Awesome Screenshot: 截长图、浏览器录屏工具。有时候有一些 pdf 只能预览不能下载，其实可以用它的截长图功能导出来 pdf
- 暴力猴：支持超多的插件，比如护眼插件、youtute 下载插件等 https://violentmonkey.github.io/ 还可以搜索插件市场 https://greasyfork.org/zh-CN
- Copytables: 可以复制网页中的表格为 html、csv 等

* `《在浏览器中嵌入 NeoVim，可使用本地配置》 <https://zhuanlan.zhihu.com/p/86027644>`_

编程字体(适合代码显示)
--------------------------------------
- Monaco (Mac)
- Consolas (Windows)
- Hack
- Source Code Pro (Adobe)
- [FiraCode(连字符特性)](https://github.com/tonsky/FiraCode)
- Jetbrinas Mono 字体
- Nerdfont [https://www.nerdfonts.com/]


代码工具/算法可视化
--------------------------------------
- codelf: https://github.com/unbug/codelf 不会命名？变量名查询神器
- python 可视化：http://www.pythontutor.com/live.html#mode=edit
- VisuAlgo: https://visualgo.net/en 算法可视化
- https://www.cs.usfca.edu/~galles/visualization/RedBlack.html
- https://github.com/krahets/hello-algo 算法可视化


代码辅助和检测工具
--------------------------------------
- pylint: 代码静态检测工具，请务必集成在你的编辑器或者IDE里（推荐）。能帮你少犯很多错误，动态语言写项目要十分谨慎，非常容易犯错。或者在CI加上 hook 每次 push 代码的时候检测。pylintrc 参考：https://github.com/PegasusWang/linux_config/blob/master/pylintrc 这里我忽略了很多无关紧要的提示，默认的 pylint 配置对代码检查实在是太严格了，很多老鸟也过不了。我敢打赌大部分 python 项目用默认 pylint 检查都是不及格分。（pylint 会给代码算个分, 10分制）
- mypy: 类型检查工具，结合 python3 的 type hint 或者 python2 中的类型注释可以做类型检查。https://mypy.readthedocs.io/en/latest/cheat_sheet_py3.html
- pep8: python代码风格检测工具(推荐)。懒人可以试试 autopep8 工具，自动格式化。所有人的代码都过一遍 pylint 和 autopep8(放宽行长度) 看起来就比较一致了。甚至可以配置编辑器保存后自动执行 autopep8，类似 gofmt
- autopep8/yapf: python 代码自动格式化工具，懒人必备。都可以集成到 vim 里，比如使用  Plugin 'Chiel92/vim-autoformat'  工具一键格式化。不过注意有时会无法正确处理多重缩进，这个比较危险，代码逻辑都变了，还是自己写代码的时候注意下格式。
- prospector: 集成了众多python代码检测工具
- mccabe: 圈复杂度检测工具。McCabe 是一种度量程序复杂度的方法，如果单个子程序复杂度过高，或许就需要拆分逻辑提高程序的易读性。
- pyflakes
- bandit: 用于Python代码的安全性分析，openstack 的项目 https://github.com/openstack/bandit
- rope，可以用来重构等，功能强大。笔者经常用rope自动帮我重新整理导入的包顺序。
- python-mode: 一个vim插件，有很多 python 补全，语法检测等支持。并且集成了很多 python 工具(pylint,pep8等)，笔者正在用。
- jedi-vim: 一个 vim 插件，python 支持补全和重构。注意和 rope 的自动补全有冲突，不要同时启用。
- Pyreverse: 代码 UML 生成工具, 帮助我们理解继承关系 (https://pythonhosted.org/theape/documentation/developer/explorations/explore_graphs/explore_pyreverse.html)
- Epydoc: Automatic API Documentation Generation for Python
- 2to3/python-modernize: python2 转 python3 工具。目前 Instagram 已经全面迁移到 python3
- 编写2/3兼容代码：http://python-future.org/compatible_idioms.html
- kite: 基于机器学习的自动补全，支持多种编辑器和 IDE https://www.kite.com/

* `《[转] Instagram 在 PyCon 2017 的演讲摘要》 <https://zhuanlan.zhihu.com/p/27232791>`_

我觉得对于动态语言使用好静态代码检测工具还是很有必要的，最好集成在你的开发工具里(比如使用vim的python-mode插件可以很容易整合这几个代码检测工具)，辅助你写出高质量代码，否则大型动态语言项目维护起来就是灾难。python会给你一种代码很好写的错觉，不严格要求经常会写出来难以维护的烂代码，甚至导致代码仓库失控。通过 pep8、pylint、mccae 检测过的代码如果警告和错误都消除以后，从代码风格来说基本是没有大问题的，笔者一开始用的时候也是各种警告，修正过很多代码警告以后，以后代码就越来越规范和整洁了。https://github.com/PyCQA 。对于懒人的话直接用 autopep8 ，再也不用纠结格式问题了。目前笔者在公司的一些后端项目中就加入了 flake8 和 pylint 检测（自定义了 pylintrc 文件忽略一些无伤大雅的警告），代码写糙了 CI 都过不了。
我个人强烈建议，所有的人用 isort 整理包导入顺序，用 autopep8 格式化代码，用 pylint 静态检测，（笔者目前的小团队就是这么做的），这样提交的代码格式会非常一致，而且代码非常干净，大项目也不容易失控，动态语言写项目真的很容易出错。能用工具就尽量用工具帮我们解决格式等问题，多余的精力用来思考代码逻辑本身。

代码质量检测平台
--------------------------------------
- Covrralls
- Sonar: https://www.sonarqube.org

项目工具
--------------------------------------
- pigar: 找出项目使用到的依赖库
- buildout: 项目构建工具
- pyenv/virtualenv/pipenv：多版本管理
- cloc, boyter/scc: 命令行代码行数统计工具，scc 速度快很多


代码仓库托管
---------------------------------------
- gitlab: 公司用得多
- github: 著名的程序员同性交友网站
- bitbucket: 类似 github，好处是支持免费的私有仓库。当你不想共享代码的时候可以用


项目模板脚手架
--------------------------------------
微服务化的时代经常需要创建很多类似的项目代码模板，这个时候项目脚手架就分方便了。
统一的项目模板对于运维和开发都比较重要，有利于降低维护成本，大家写的代码结构都比较一致非常有利于维护和迁移模块。

- cookiecutter: 一系列项目模板生成工具，懒人必备。https://github.com/audreyr/cookiecutter。笔者之前内部项目就直接用 flask-cookiecutter 直接生成的。
  可以到 http://cookiecutter-templates.sebastianruml.name/ 搜索感兴趣的编程语言或者框架的代码模板直接拿来修改使用
- yeoman: http://yeoman.io/generators/ 前端项目模板生成工具
- ant-design: 后端管理后台项目解决方案 https://ant.design/docs/react/practical-projects-cn


持续集成
--------------------------------------
- gitlab
- Travis CI
- Jenkins
- Sonar: https://www.sonarqube.org/ 代码质量管理

配置中心
--------------------------------------
- Apollo: https://github.com/ctripcorp/apollo
- Spring Cloud Config
- Disconf

Api 工具
--------------------------------------
- checklist: http://python.apichecklist.com/

DSL
--------------------------------------
- PLY
- PyParsing: 用来实现 DSL 比较方便。
- Parsley


测试工具
--------------------------------------
- py.test
- nosetest
- unittest
- tox
- mock: mocking makes unit testing easier

文档/写书/笔记工具
--------------------------------------
- google doc/石墨: 支持多人协作编辑
- gitbook/docsify/docusaurus + markdown: 可以写文档或电子书，托管到 github 上，可以生成 pdf。
- doocer: http://doocer.com/ 写 kindle 电子书工具
- sphinx + readthedoc(或者 mkdocs，支持 markdown) （代码即文档），python 项目很多在用这个生成文档。这本小书就是这么写出来的。`编写《Redis 设计与实现》时用到的工具 <http://blog.huangz.me/diary/2013/tools-for-writing-redisbook.html>`_
- swagger/apidocjs: 适合写 restful 文档。如果使用 grpc 可以直接生成。
- jupyter(ipython) notebook，可以做笔记或者代码演示或者ppt，支持rst，md等格式，搞数据科学的人用得比较多，配合 RISE (https://github.com/damianavila/RISE) 可以做代码交互式 slideshow，非常好的工具
- Confluence: 适合作为团队的项目文档工具，团队大了以后文档还是很重要的
- vimwiki/emacs org-mode: 依赖于vim/emacs 编辑器，可以做个人笔记，不过笔者还是比较倾向于独立于编辑器的工具
- Graphviz: 通过编写代码来生成图片 http://graphviz.org/
- pandoc: 用于各种格式文档之间的转换，比如 html->markdown, html->rst, markdown->rst
- Onenote: 微软出品笔记工具，手写和绘图功能很不错，笔者在一些教程里使用它来绘图演示

参考: `Self-publishing a book with reStructuredText, Sphinx, Calibre, and vim <https://digitalsuperpowers.com/blog/2019-02-16-publishing-ebook.html>`_

Swagger 工具
--------------------------------------
- swagger编辑器: https://swagger.io/tools/swagger-editor/
- swagger-edit: https://github.com/huan/swagger-edit 本地编写文件预览，可以用自己喜欢的编辑器了（依赖 docker)


静态博客工具
--------------------------------------
静态建站工具允许我们用 github pages 建立静态博客，省去了服务器的费用。笔者的 https://pegasuswang.github.io 就是基于 hexo 搭建

- hexo: 基于 nodejs 编写的静态博客工具 https://hexo.io/zh-cn/
- hugo: https://gohugo.io/ go 编写的静态博客建站工具
- gitalk: https://github.com/gitalk/gitalk#install  基于 github 的评论系统

日志、异常收集工具
--------------------------------------

- Sentry: 用来记录异常非常好用，能看到完善的栈信息，方便排错。Python 社区用的比较多
- Fluentd
- ELK: Elasticsearch, Logstash, Kibana 日志聚合和搜索系统

管理及运维、监控工具(devops很火)
--------------------------------------
- Supervisor.进程管理
- Fabric(封装了paramiko).应用部署
- docker/k8s.最近比较火的容器技术。很多采用微服务架构的公司使用 docker 作为容器部署服务，或者构建一致的开发环境
- SaltStack和Ansible. 配置管理
- StatsD\Graphite\Prometheus等web监控
- Netdata: 强大的系统监控工具 https://github.com/netdata/netdata
- glances: 支持终端监控 https://github.com/nicolargo/glances

API gateway
--------------------------------------
- kong: open-source API gateway and a microservices management layer. https://github.com/Kong/kong


调试工具
--------------------------------------
- IPython/Bpython: 代替原生的解释器，支持补全，语法高亮等
- ipdb/pdb: ipdb 支持自动补全，比原生的 pdb 要好用一些。
- pdbpp: https://pypi.org/project/pdbpp/
- postman: 接口调试 gui 工具，也可以导出成各种编程语言的 HTTP 请求代码，或者粘贴请求地址并且修改参数
- curl: 如果不想使用 postman 等 GUI 工具（比如在服务器上本地测试无法使用这种工具），可以用 curl 命令或者 python requests 库模拟请求
- https://curl.trillworks.com/ 把 curl 命令参数转成 requests 代码。 https://github.com/NickCarneiro/curlconverter/。
- https://curlconverter.com/ 类似的 curl 请求转成 代码。可以安装命令行工具(不过似乎当前需要 node v16.15.1 版本)
- httpie : 类似 curl 但是参数更加友好的命令行请求工具
- httpbin.org 一个使用 flask 编写的 http 调试网站，你可以通过 http 客户端发送请求到该网址验证 http 参数等
- curl/requests 互相转化: https://github.com/oeegor/curlify https://github.com/spulec/uncurl
- Violentmonkey: 油猴脚本。有比较多插件 https://greasyfork.org/zh-CN 可以搜索使用

调试小技巧：使用 chrome 开发者工具右键请求点击copy as curl，然后可以用 uncurl 转成 requests请求调试代码。


抓包/网络工具
--------------------------------------
- mitmproxy: 用 python 实现的终端命令行http抓包工具，可以将请求直接导出成 curl 请求，python 代码甚至 locust 测试脚本，非常方便，笔者经常用来抓包和调试。
- charles: mac下的 http抓包软件(收费)。注意如果 https 乱码：菜单栏 Proxy–>SSL Proxying Setting–>选择SSL Proxying——>点击add在弹框中port里填写443(443代表通用https端口号)， host中的*代表抓取所有地址的包。
- wireshark: 支持tcp抓包，对于一些使用自有协议的抓包，没法通过 http 请求抓包，可以使用 wireshark。wireshark是学习网络协议的好帮手
- termshark: 类似 wireshark 的一个命令行版本的抓包工具 https://github.com/gcla/termshark
- tcpdump: 服务器命令行抓包工具
- netwox: 网络工具集，可以用来创造任意的 TCP、UDP 和 IP 数据报文

参考:

- `Wireshark抓包iOS入门教程  <http://mrpeak.cn/blog/wireshark/>`_


Proxy
--------------------------------------
- proxychains-ng/privoxy: 把socks5 转成 http代理


爬虫相关
--------------------------------------
- Scrapy: 知名的爬虫框架。生态比较丰富
- pyspider: 国人写的一个不错的爬虫框架
- requests: 一般小爬虫用 requests 绰绰有余。
- lxml/BeautifulSoup/pyquery: 解析 html，xml 等。
- tornado: 异步的 http client 可以写爬虫
- redis/celery: 实现队列、异步爬虫。异步方案也比较多
- phantomjs/puppeteer/playwright-python: 用来处理动态网站。puppeteer 基于 nodejs。可以用来写爬虫，控制浏览器，自动化测试等
- pyppeteer/selenium: 基于 python 动态网站爬虫处理，或者用于自动化测试
- portia: 类似造数、八爪鱼之类的可视化爬虫 https://github.com/scrapinghub/portia
- Pholcus/Colly/crawlab: Go语言编写的爬虫框架

自动化测试
--------------------------------------
- uiautomator2: https://github.com/openatx/uiautomator2
- taobao-iphone-device: https://github.com/alibaba/taobao-iphone-device

异步任务框架
--------------------------------------
- celery: python 社区一个流行的异步任务框架
- machinery: golang 的异步任务框架 https://github.com/RichardKnop/machinery
- Airflow: 任务调度 https://airflow.apache.org/docs/apache-airflow/1.10.1/index.html#
- xxl-job: 分布式任务调度平台 https://github.com/xuxueli/xxl-job/

参考：https://zhuanlan.zhihu.com/p/92152648 Python 定时任务最佳实践

python定时任务框架
--------------------------------------
- schedule：Python job scheduling for humans. 轻量级，无需配置的作业调度库
- python-crontab： 针对系统 Cron 操作 crontab 文件的作业调度库
- Apscheduler：一个高级的 Python 任务调度库
- Celery： 是一个简单，灵活，可靠的分布式系统，用于处理大量消息，同时为操作提供维护此类系统所需的工具, 也可用于任务调度

端口扫描
--------------------------------------
ZMap: 是密歇根大学研究人员发布的软件，可以在千兆网络条件下 45 分钟完成全网单端口扫描。支持 TCP SYN 、ICMP、UDP 等多种模式。可以用来搜寻代理

后台管理
--------------------------------------
- Ant Design Pro: 基于 react 的后台管理方案，可以用来快速搭建后台运营 or 管理
- flask-admin/Django admin: 框架自带的后台管理。flask-admin 也有类似功能

RPC
--------------------------------------
- thrift: facebook 开源的 rpc 框架，很多大公司在使用
- grpc: grpc是一个高性能、开源和通用的 RPC 框架，面向移动和 HTTP/2 设计。目前提供 C、Java 和 Go 语言版本，分别是：grpc, grpc-java, grpc-go. 其中 C 版本支持 C, C++, Node.js, Python, Ruby, Objective-C, PHP 和 C# 支持. https://github.com/grpc/grpc

Rest
--------------------------------------
- Django Rest Framework(DRF): https://www.django-rest-framework.org/
- Flask-Restful: https://flask-restful.readthedocs.io/ ，可以用 cookiecutter-flask-restful 快速启动一个 restful 后端项目
- fastapi: https://github.com/tiangolo/fastapi python3 异步框架
- GRPC: https://github.com/grpc-ecosystem
- Gin: go web 框架

数据处理和可视化
--------------------------------------
- pandas: 处理报表经常用，非常适合处理矩阵、DataFrame、excel 等。配合一些前端可视化库可以弄报表啥的。碰到  Excel
  处理的强烈建议使用。录了一个小视频讲了下简单的 pands 处理 excel https://zhuanlan.zhihu.com/p/37654682
- matplotlib: python 绘图。数据可视化有很多其他 python 和前端解决方案


压测(benchmark)工具
--------------------------------------
- locust: 基于 python gevent 实现的压测工具。http://locust.io/， 有 web 界面，支持编写 python 脚本模拟测试，高度定制化。
  https://github.com/SvenskaSpel/locust-plugins 支持插件实现更多协议和压测功能。好处是压测脚本可以用版本库管理起来复用
- ab/wrk/siege: 常见的命令行测试工具，用于一些简单的压测
- JMeter: 基于 Java 的压测工具
- pts: 阿里云提供的一个压测工具。https://cn.aliyun.com/product/pts

一些 web 框架的压测结果：

- https://github.com/the-benchmarker/web-frameworks
- https://www.techempower.com/benchmarks/

Profiler 性能分析工具
-------------------------------------------------------------------------
- pyflame: https://github.com/uber/pyflame 火焰图工具，分析 cpu 耗时
- pyinstrument:https://github.com/joerick/pyinstrument  python 执行耗时分析工具

APM (Application Performance Management)
-------------------------------------------------------------------------
- Zipkin: https://link.zhihu.com/?target=https%3A//github.com/openzipkin/zipkin


参考：https://www.zhihu.com/question/27994350

数据库命令行/可视化工具
--------------------------------------
- mycli: mysql 命令行补全等。https://github.com/dbcli/mycli
- MysqlWorkbench/Sequel Pro: mysql 客户端工具。也可以用来生成生成 ER 图
- Dbeaver 跨平台的mysql/sqllite等可视化工具。mac可以通过 ``brew install --cask dbeaver-community`` 安装
- Navicat Premium: 强大的数据库管理工具，收费
- pt-online-schema-change: mysql数据库变更工具
- Medis: redis client 工具
- MongoChef: Mongodb 客户端工具

- gen: 根据 mysql 生成 golang gorm model。https://github.com/smallnest/gen
- sqlacodegen: 从 mysql 生成python sqlalchemy model定义。https://github.com/agronholm/sqlacodegen

参考：https://www.webucator.com/article/how-to-create-an-er-diagram-for-a-mysql-database-w/


绘图/流程图/思维导图工具
--------------------------------------
- processon: http://processon.com/ 使用了下感觉还不错，支持流程图、时序图、思维导图等，可以 clone 别人看好的图作为模板
- draw.io: https://www.draw.io/  UML 图的功能比较好用，笔者一般流程图用 processon，UML和时序图一般用 draw.io(可以导入飞书)
- echart.js: 数据可视化 https://echarts.apache.org/examples/zh/index.html
- 亿图：www.edrawmax.cn 类似 processon，有很多好看的模板
- Gliffy Diagrams: https://chrome.google.com/webstore/detail/gliffy-diagrams/bhmicilclplefnflapjmnngmkkkkpfad/related
- carbon/codeimg.io: https://carbon.now.sh/ 可以根据代码生成图片，在分享代码却没有高亮的时候比较方便。codeimg 类似
- colorhunt: 配色方案（很多程序员的图配色不好看，可以学习一些好看的配色方案) https://colorhunt.co/
- excalidraw: 手写风格绘图 https://excalidraw.com/
- onemodel: 程序员绘图，有很多编程图标 https://www.onemodel.app/

量化投资(偏向python量化)
--------------------------------------
- tushare: https://github.com/waditu/tushare 有本小白参考书: https://wizardforcel.gitbooks.io/python-quant-uqer/
- efinance: https://github.com/Micro-sheep/efinance efinance 是一个可以快速获取基金、股票、债券、期货数据的 Python 库，回测以及量化交易的好帮手
- akshare: https://github.com/akfamily/akshare  开源财经数据接口库

效率，时间管理工具
--------------------------------------
不像计算机，人脑其实不善于多进程工作（基于脑科学研究），最好一次做好一件事情，如果中间有各种任务穿插，可以用 todolist 工
具记录之后分配轻重缓急统一处理，减少大脑的负荷。

- teambiation/trello: todo list 工具，管理任务。今天做了什么；计划做什么；哪些困难导致工作被阻塞(实在搞不定的记下来及时向同事求助)；发现了什么问题；今天学到了什么。(类似于开发日志之类的玩意，每天都是真正做了事情的，并且最好每天都是学到了新东西的)。有时候一些小灵感或者解决问题的思路在没有纸笔的情况下也能迅速记录到工具里，防止遗忘。
- 番茄工作法：人长期专注的时间是有限的，找到适合自己的最佳番茄钟，并且每个时间段都专注于一件事，每件事分清轻重缓急，要事优先。在休息时间处理喝水、上厕所等杂事，做几个深呼吸给脑瓜子充点氧，或者活动下筋骨，眺望下远处。预防职业病（最近有看到工程师视网膜脱落的，要重视身体健康）。
- Be Focused: mac 下番茄工作法工具，可以用来给任务计时，或者提醒该休息下了
- 复盘。无论是写代码、做需求、改bug等，事后反思总结。分析并且记录耗时的地方和可以改进的地方(怎么让自己涨点记性，整理 checklist)，对于一些错误或者坑也可以记录成文档当做团队的知识财富。
- zapier: https://zapier.com/ 一个连接 app 自动化工作流的工具，比如可以用来定期提醒发邮件等，非程序员也能实现定时任务啦

程序员外设/健康工具
--------------------------------------
- 键盘/鼠标腕垫：长时间使用键盘手腕压力比较大，可以考虑买一个几十块的软垫放在键盘下边托住手腕，减轻手腕压力
- 主动降噪耳机和纯音乐：选择类似于《阿尔法波高效记忆音乐》《巴洛克学习音乐》等，能帮助你隔绝噪音，或者你可以在youtube/网易云音乐等搜索到很多类似工作或学习音乐(搜优美钢琴曲)。反正笔者听歌的时候会想歌词反而会打扰思路，一般就是听这种不怎么让你瞎想的音乐。降噪耳机如果不差钱可以考虑主动降噪耳机(WI1000X/QC30)，效果好一些，网上也有一些对比视频。对于嘈杂的工作环境来说，绝对是一个非常值得的投资。
- 人体工学座椅/鼠标/键盘/usb 屏幕挂灯，土豪必备
- 办公室午休床，隔音耳塞
- 海露人工泪液/湿房镜/防蓝光镜片/usb热敷眼罩: 缓解干眼症
- 录音笔。最近裁员有点多，你懂的。笔者用的一款搜狗的录音笔，非常小巧，可以用来记录会议，语音转文字做字幕，实时翻译等。
- 机械/静电容键盘（键盘可以说是程序员最在意的工具了，推荐几个我个人认为比较适合写代码的，个人推荐红轴，无段落感，打字行云流水)

  - HHKB: 码农神器静电容键盘，不过不用 vim，非 linux/unix 用户慎用。没有方向键和F区
  - 宁芝（niz）PLUM普拉姆静电容键盘: 同静电容键盘，键位更多，适合大众用户
  - 阿米洛（Varmilo） 苹果MAC双系统机械键盘: 机械键盘，适合 mac
  - Poker2: 键位类似 HHKB，同样是可编程迷你键盘，可以替代 HHKB，笔者之前长期使用
  - Filco Minila Air: 同样是迷你机械键盘，适合大众程序员

参考: `程序员双十一剁手指南  <https://zhuanlan.zhihu.com/p/89192238>`_

视频课程录制(vlog工具)
--------------------------------------
在 mac 下录制了一些 vim 和 python 的视频教程(b 站或者知乎可以看到)，记录下使用到的一些硬件和软件工具，硬件工具均可网购，部分软件收费：

- keycastr: mac 按键回显到屏幕，最近录制 vim 视频教程的时候有用到。https://github.com/keycastr/keycastr
- youbute-dl/lux(golang): https://github.com/rg3/youtube-dl 命令行油管视频下载工具
- aria2: https://aria2.github.io/ 轻量级的命令行下载工具
- FFmpeg: 强大的视频处理工具，可以用来截图，截取视频片段等
- ScreenFlow/Camtasia/Obs: 屏幕录制，剪辑工具，收费。笔者用来录制屏幕用
- licecap: 一款小巧的免费 gif 录制工具
- TunesKit Video Cutter(mac): 视频分割、合并工具
- iZotope RX6: 音频降噪工具，去除杂音、呼吸声等等，收费
- Audacity: 音频处理 https://www.audacityteam.org/download/
- MediaInfo: 查看视频信息
- HandBrake: 视频压缩工具，免费工具。直接从录屏工具导出的视频体积可能会非常大，推荐压缩后上传到网站
- SketchBookPro/Deskscribble(收费): 白板/黑板工具，配合 wacom 手写板可以把屏幕当成黑板或者白板使用。模仿可汗学院的授课方式，笔者在讲述 Python 算法的课程里使用到。
- Wacom/绘王 手绘板：用来实现屏幕手写，配合绘图或者白板软件当做黑板使用，方便手写做一些演示或者推导。
- Blue yeti电容麦/Rode NT usb电容麦/铁三角Atr2100动圈麦：使用 mac 内置麦克风音频效果比较差，可以考虑专业的播客级麦克风，录制出来的视频声音要清楚很多。usb 麦克风即插即用，非常方便，但是灵敏底噪大。动圈麦在嘈杂环境表现更好，不会收录杂音。
- VideoScribe: 制作手绘风格视频，提升视频趣味性。收费
- 课件制作: PowerPoint, Keynote, AxeSlide, Focusky 等。笔者现在喜欢使用 OneNote 配合手写板在视频里进行图解演示。
- Mousepose: 鼠标高亮增强工具。演示的时候可以高亮部分区域，其他部分置灰
- 免费字体：思源字体(思源宋体、思源黑体)；站酷字体。视频中的一些字体可能要考虑版权问题，推荐使用无版权字体
- canva: 一个好用的封面设计网站，可以用来设计 vlog/课程 视频封面图 https://www.canva.com
- qmcdump: 命令行版本的 qq 音乐解码器

MacOS 图片软件
--------------------------------------
- ImageOptim: https://imageoptim.com 一个开源免费的mac图片压缩工具
- iShot: 一个强大的 macos 截图、截长图软件(截长图比较好用)

HTML Presentation Tools
--------------------------------------
如果觉得用 ppt 做分享比较老套，可以尝试一些使用 HTML 来做 slide show 的工具。或者使用 markdown 生成 html 幻灯片。

- slidev: nodejs 编写 https://github.com/slidevjs/slidev (推荐，有标注功能)
- reveal-md: 使用 markdown 转成网页 slides。https://github.com/webpro/reveal-md 亲测使用起来很方便，依赖 nodejs
- reveal.js: The HTML Presentation Framework
- RISE: 在 jupyter 里做 slide show，甚至可以直接在网页里运行 Python 代码。 https://github.com/damianavila/RISE
- remark: A simple, in-browser, markdown-driven slideshow tool. https://github.com/gnab/remark
- md2googleslides: markdown 转成google slides  https://github.com/gsuitedevs/md2googleslides

* `《HTML-presentation-tools.md》 <https://gist.github.com/PegasusWang/5d00c2e32943f1e3258e964eb64ce4aa>`_
* `《markdown-for-slide-decks.md》 <https://gist.github.com/johnloy/27dd124ad40e210e91c70dd1c24ac8c8>`_

Terminal slides
--------------------------------------
在终端下使用 markdown 演示

- slides: go 编写的终端 ppt 工具 https://github.com/maaslalani/slides
- present: python 语言的终端演示工具 https://github.com/vinayak-mehta/present

思维导图工具
--------------------------------------

- coggle.it: 一款免费的在线思维导图工具 https://coggle.it/
- GitMind: 在线思维导图工具，可以多人协作 https://gitmind.cn/

电子阅读器/电子书软件
--------------------------------------
笔者使用的 Kindle 和 国产的大屏幕 Boox，目前小米生态的墨案也推出了大屏幕(10.3)寸水墨屏阅读器。
当然你可以使用平板电脑，不过长时间盯着屏幕对眼睛不太好，笔者倾向于使用水墨屏阅读器。

- Koreader: http://koreader.rocks/ 一款支持多种主流电子书格式的开源电子书阅读器，支持Kindle/Android等
- calibre: https://calibre-ebook.com 跨平台的电子书管理和阅读桌面软件

参考：

* `《Kobo Aura One刷机折腾记录：激活、安装koreader、中英字体、字典》 <http://www.dealwithem.com/3457282/>`_

Linux network debug Tools
--------------------------------------
注意：dig/nslookup 等直接请求 dns server，会忽略 etc/hosts

- ping/tcping：特定域名的 ip 是否可达。ping send ICMP echo request

  - ping google.com
  - ping -c 3 google.com

- dig/host: get DNS records。用来替代 nslookup

  - dig google.com 默认返回 A 记录
  - dig google.com MX
  - dig -x 8.8.8.8 反向查询
  - host -a google.com 类似dig
  - host 8.8.8.8

- route: shows and manipulate ip routing table
- traceroute 诊断网络延迟。诊断到目标路径的设备延迟

  - traceroute google.com  命令返回的星号指示丢失包
  - traceroute -n google.com , to avoid reverse dns lookup use -n
  - traceroute -I google.com, send ICMP packet (default UDP, -T TCP, some servers block UDP)

- mtr, realtime tracing, 结合了ping,traceroute,nslookup的相关特性
- ss(socket statistics), checking connection performance。socket 统计，比netstat快，利用了 tcp_diag

   - https://www.cnblogs.com/peida/archive/2013/03/11/2953420.html

- arp, view the arp table
- tcpdump, packet analysis。https://juejin.cn/post/6844904084168769549

  - tcpdump -i <network_device> tcp
  - tcpdump -i <network_device> port 80
  - tcpdump -c 20 -i <network_device> port 80 , -c number of events
  - tcpdump -c 20 -i <network_device> src XXX.XXX.XXX.XXX
  - ifconfig, you can obtain the device names likes this。查看和配置机器网卡
  - tcpdump -w /path/ -i <network_device>, tcpdump to a file
  - tcmpdump -r /path
  - sudo tcpdump -i lo0 port 6379 -nnX -vvv -A  # 本地 redis 抓包

- netstat, network statisic,  display connection info, routing table information etc
- lsof(查看端口进程): lsof -i:8000
- iftop: 查询流量异常的进程
- curl: 发送 http 请求，类似的还有一些比如 httpie
- nc: 作为tcp|udp服务器,或者作为工具,模拟发送tcp,udp包
- trickle: 用户空间带宽控制管理的工具
- Nmap: 端口扫描工具

Linux debug Tools
--------------------------------------

- gdb
- valgrind
- ltrace: tracing system and library calls
- strace —— Trace system calls and signals。 跟踪进程的系统调用或信号产生的情况。
- lsof: tracking open files
- pmap: viewing memory allocation
- fuser file_name 或者 ``ls -l /proc/*/fd/* | grep filename`` 找到文件被哪些进程使用

命令行工具
--------------------------------------

- https://github.com/agarrharr/awesome-cli-apps
- https://github.com/chubin/awesome-console-services
- https://github.com/herrbischoff/awesome-command-line-apps


参考：
--------------------------------------

- https://likegeeks.com/linux-network-commands/
- https://unix.stackexchange.com/questions/50098/linux-network-troubleshooting-and-debugging
- https://www.tecmint.com/linux-network-configuration-and-troubleshooting-commands/
- https://github.com/mrzool/unix-as-ide
