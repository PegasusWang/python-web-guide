.. _goweb:

Go 入门和深入
=====================================================================

Go语言入门和深入
--------------------------------------------------

- `Go Roadmap <https://github.com/Alikhll/golang-developer-roadmap>`_  学习路线图
- `Lets Go <https://github.com/PegasusWang/LetsGo>`_  笔者连载的 go 文字和视频教程
- `A Tour of Go <https://tour.golang.org/welcome/1>`_
- `Go by Example <https://gobyexample.com>`_
- `Learn Go with Tests <https://quii.gitbook.io/learn-go-with-tests/>`_
- `The-way-to-go <https://github.com/Unknwon/the-way-to-go_ZH_CN>`_
- `golang-developer-roadmap <https://github.com/Alikhll/golang-developer-roadmap>`_
- `How to Write Go Code <https://golang.org/doc/code.html>`_
- `Learning-golang <https://github.com/developer-learning/learning-golang>`_
- `Build Web Application With Golang <https://github.com/astaxie/build-web-application-with-golang>`_
- `Go 高级编程 <https://chai2010.cn/advanced-go-programming-book/>`_
- `Go 101 <https://go101.org/article/101.html>`_ 包含了很多基础和高级主题
- `Mastering Go <https://books.studygolang.com/Mastering_Go_ZH_CN/>`_
- `Go语言圣经 <https://books.studygolang.com/gopl-zh/>`_
- `Go安全编程规范 <https://github.com/Tencent/secguide/blob/main/Go%E5%AE%89%E5%85%A8%E6%8C%87%E5%8D%97.md>`_
- `Go并发编程 <https://lailin.xyz/post/go-training-week3-goroutine.html>`_
- `Learning notes for golang <https://github.com/jincheng9/go-tutorial>`_


Go 常用框架(工具)技术雷达 ❤️
---------------------------------------------------------------
技术选型一般选择接口稳定，持续维护，生态相对成熟，star 数量较高，用户广泛的库，坑少一点。
前后分离时代用 gin 之类的框架写app后台还是挺快的，但是感觉做并发不高的内部后台业务还是用脚本python/php之类的更快。
以下第三方库均可以通过 google + 关键词搜索到，同一行尽量按照流行程度从前往后列举，默认都是 github 上的包(只写了仓库后缀)。
也可以去 awesome-go 之类的去查找，然后根据 star 数目等作为参考选用。

- web/rpc框架: gin, grpc, beego, labstack/echo
- 微服务框架：go-kit, go-micro, karatos(b 站)，go-zero(好未来)，jupiter(斗鱼)
- 参数验证：go-playground/validator, bytedance/go-tagexpr
- 单元测试断言：matryer/is, testify/assert, smartystreets/goconvey(bdd 驱动测试), rakyll/gotest(gotest 颜色)
- 错误处理: pkg/errors, hashicorp/go-multierror(多错误处理), sync/errgroup(多goroutine错误处理)
- panic处理：thepkg/recover
- 重试：avast/retry-go
- json处理转换：go-simplejson/mapstructure，json-iterator/go (比内置的 json 解析快很多), tidwall/gjson(获取 json 值), bytedance/sonic
- 字典/结构体合并/结构体拷贝/类型转换：imdario/mergo, jinzhu/copier, jmattheis/goverter
- 配置解析: viper(兼容很多格式)
- mysql orm: gorm, xorm, sqlx, ent/ent(实体框架), doug-martin/goqu(生成sql)
- redis: go-redis, redigo
- Kafka: Shopify/sarama, confluent-kafka-go
- Elasticsearch: olivere/elastic, elastic/go-elasticsearch
- mongodb: mongodb/mongo-go-driver
- id生成器: rx/xid, beinan/fastid, bwmarrin/snowflake, sony/sonyflake, godruoyi/go-snowflake
- uuid: gofrs/uuid, satori/go.uuid, google/uuid (注意有些会 panic)
- hash: cespare/xxhash(快速 hash), groupcache/consistenthash(一致性哈希)
- cache(in memory并发安全): patrickmn/go-cache, allegro/bigcache, golang/groupcache(分布式), coocood/freecache, singleflight(防止缓存击穿), dgraph-io/ristretto, orcaman/concurrent-map(泛型)
- cache(基于context): ag9920/go-ctxcache (基于context缓存解决重复调用放大问题)
- cache(lru/lfu/2Q/ARC): hashicorp/golang-lru, bluele/gcache, songangweb/mcache(增强lru)
- 并发/协程池(star 数从低到高排序)：

  - https://github.com/panjf2000/ants
  - https://github.com/rafaeldias/async
  - https://github.com/Jeffail/tunny
  - https://github.com/benmanns/goworker
  - https://github.com/buptmiao/parallel

- 原子访问：uber-go/atomic
- 异步任务队列框架: machinery, gocelery, hibiken/asynq, LMSTFY(美图开源)
- 分布式/定时任务: robfig/cron, ouiqiang/gocron, distribworks/dkon, shunfei/cronsun
- 熔断：hystrix-go, eapache/go-resiliency, cep21/circuit, alibaba/sentinel-golang
- 限流库:

  - web框架限流：ulule/limiter, didip/tollbooth
  - 令牌桶(token bucket)限流：juju/ratelimit, golang.org/x/time/rate
  - 漏桶(leaky bucket)限流: uber-go/ratelimit

- 日志: logrus, zap, lumberjack(滚动日志)
- 链路追踪：opentracing/opentracing-go, uber/jaeger-client-go
- 调试：go-spew/dlv, kr/pretty
- 图片处理：h2non/imaginary
- 网络库/连接池：fatih/pool; panjf2000/gnet, valyala/fasthttp，kavu/go_reuseport
- websocket: nhooyr.io/websocket, gorilla/websocket
- http client: levigross/grequests, asmcos/requests, go-resty/resty, gojek/heimdall(重试、熔断)
- 表格：go-echarts
- excel(XLSX): 360EntSecGroup-Skylar/excelize, tealeg/xlsx
- 转换工具：

  - sql2go(sql -> go struct): http://stming.cn/tool/sql2go.html
  - curl2go(curl -> go http code): https://mholt.github.io/curl-to-go/
  - Json2go(json -> go struct): https://mholt.github.io/json-to-go/

- 代码检查工具：

  - 静态检查：golangci-lint
  - goroutine 泄露检查: github.com/uber-go/goleak
  - 注释工具: github.com/cuonglm/gocmt 自动给导出变量、函数等增加注释

- 热编译工具：gowatch
- 网络代理：goproxy
- 命令行处理: spf13/pflag, spf13/cobra
- 字符串处理工具：huandu/xstrings
- 通用数据类型转换：spf13/cast
- HTML 处理/过滤: PuerkitoBio/goquery, microcosm-cc/bluemonday
- 系统信息收集：shirou/gopsutil
- go runtime: bmhatfield/go-runtime-metrics(runtime 指标收集)
- 邮件：gopkg.in/gomail
- 接口文档生成：swaggo/swag
- 消息队列：nsqio/nsq
- 延时队列/时间轮：ouqiang/delay-queue, RussellLuo/timingwheel
- 分布式kv存储：etcd
- 用户认证：golang-jwt/jwt,dgrijalva/jwt-go(弃用), authelia/authelia
- 访问(权限)控制：casbin/casbin
- 进程控制：uber-go/automaxprocs
- 地理位置：ip2location/ip2location-go
- 时间处理：jinzhu/now
- 金融数字格式化/定点数: leekchan/accounting, shopspring/decimal
- 分布式事务：yedf/dtm
- 分布式锁: go-redsync/redsync(redlock算法), bsm/redislock, go-zero/core/stores/redis
- Zookeeper: go-zookeeper/zk
- 设计模式：tmrts/go-patterns
- 数据结构：deckarep/golang-set, emirpasic/gods
- 通用泛型工具库：thoas/go-funk
- 通用工具库：duke-git/lancet
- 深拷贝：mohae/deepcopy, barkimedes/go-deepcopy
- 采样监控：mosn/holmes(排查OOM等问题)
- 规则引擎：govaluate, goengine, gorule

工具:

- https://github.com/smallnest/gen gorm struct 生成工具，根据 sql 生成 struct，甚至还可以直接生成增删改查的代码
- https://mholt.github.io/json-to-go/ json 转 go struct
- https://protogen.marcgravell.com/decode proto decode 工具
- https://gopherize.me/  一个好玩的小工具，设计你喜欢的 gopher 形象
- https://github.com/egonelbre/gophers 各种好玩的 gopher 吉祥物图片
- https://github.com/jfeliu007/goplantuml 一个自动根据 go 项目生成 uml 图的工具 https://www.dumels.com/
- https://github.com/TrueFurby/go-callvis 查看 go 的调用关系
- https://github.com/novalagung/gorep 批量替换引入的包(比如修改了名字或者包名等)
- https://github.com/better-go/go-template go 生成项目模板
- https://awesome-go.com/ 寻找你需要的 go 依赖库

Go Books
---------------------------------------------------------------
- https://github.com/dariubs/GoBooks

Go 开发工具
---------------------------------------------------------------
- Goland IDE
- Vscode/Sublime/Atom 等常用编辑器结合插件
- vim/Neovim + vim-go + coc.nvim

博客:

- https://octetz.com/docs/2019/2019-04-24-vim-as-a-go-ide/
- https://ictar.xyz/2019/05/14/an-overview-of-go-tooling/
- https://github.com/fedir/go-tooling-cheat-sheet/blob/master/go-tooling-cheat-sheet.pdf

Go 博客教程
--------------------------------------------------
- https://yourbasic.org/golang/
- https://golangbot.com/learn-golang-series/
- https://golangbot.com/learn-golang-series/


Go 设计模式
--------------------------------------------------
- https://github.com/senghoo/golang-design-pattern  代码示例
- https://golangbyexample.com/all-design-patterns-golang/ go 设计模式(考虑并发安全)


Go idioms
--------------------------------------------------
- https://yourbasic.org/golang/switch-statement/


Go 错误处理
--------------------------------------------------
- https://github.com/pkg/errors 推荐使用
- https://github.com/juju/errors
- https://blog.golang.org/error-handling-and-go
- https://dave.cheney.net/2016/04/27/dont-just-check-errors-handle-them-gracefully
- https://zhuanlan.zhihu.com/p/82985617 Golang error 的突围
- https://cloud.tencent.com/developer/article/1999877 3种方式！Go Error处理最佳实践
- https://medium.com/@dche423/golang-error-handling-best-practice-cn-42982bd72672 Golang 错误处理最佳实践

Go日志实践
--------------------------------------------------
- https://imhanjm.com/2017/05/19/go%20logger%20日志实践/

Go文档查询
--------------------------------------------------
- https://gowalker.org


GOPROXY 代理
--------------------------------------------------
如果有有一些库拉不下来又没有自己的代理，可以试试

export GOPROXY=https://goproxy.io


Web/RPC框架
--------------------------------------------------

- gin
- grpc

个人推荐使用 gin，当然你可以参考一下 star 选择别的框架

- https://github.com/gin-gonic/contrib gin各种组件
- https://github.com/e421083458/gin_scaffold gin 脚手架
- https://github.com/mingrammer/go-web-framework-stars

Gin example
--------------------------------------------------
- https://github.com/EDDYCJY/go-gin-example
- https://github.com/vsouza/go-gin-boilerplate
- https://github.com/gothinkster/golang-gin-realworld-example-app
- https://github.com/go-programming-tour-book/blog-service 《go 编程之旅》博客代码示例

gin 实战博客:

- https://segmentfault.com/a/1190000013808421  gin 连载博客
- https://www.cnblogs.com/xinliangcoder/p/11212573.html logrus日志
- https://marcoma.xyz/2019/03/17/gin-tutorial-7/
- https://www.jishuchi.com/books/gin-practice Golang Gin 实践

微服务
--------------------------------------------------
微服务框架：

- go kit: https://github.com/go-kit/kit
- go-micro: https://github.com/micro/go-micro
- kratos: https://github.com/bilibili/kratos B站go微服务框架
- go-zero: https://github.com/tal-tech/go-zero 好未来 go 微服务框架
- jupiter: https://github.com/douyu/jupiter 斗鱼 go 微服务框架

微服务代码示例：

- https://dzone.com/users/3214037/eriklupander.html 介绍 go 微服务实践的一系列博客
- https://github.com/callistaenterprise/goblog go 微服务代码示例和博客，介绍了微服务各种基础组件
- https://github.com/yun-mu/MicroServicePractice 微服务实践

Go package (搜索常用的 go 第三方库)
--------------------------------------------------
- https://awesome-go.com/
- https://go-search.org/search?q=redis
- https://golangrepo.com/

Go项目Layout
--------------------------------------------------
- https://github.com/golang-standards/project-layout 标准 go 项目目录组织
- https://zhengyinyong.com/go-project-layout-design.html


单元测试(unittest)
--------------------------------------------------

`GoMock框架使用指南 <https://www.jianshu.com/p/f4e773a1b11f>`_
`如何写出优雅的 golang 代码 <https://draveness.me/golang-101>`_

静态语言编写单测相比动态语言要难一些，动态语言中比如 python 可以很容易用 mock.patch 来做属性/方法替换。
但是静态语言不行，一般难点在于如何去模拟外部依赖(比如数据库/rpc请求，redis 请求等)：

- 接口(go 推荐面向接口编程，否则你很难使用 gomock 来编写单测)
- mysql: 如何 mock 数据库请求。使用 sqlmock，或者编写 dao 层 interface，然后 mock 这个dao层接口
- http: 使用 httpmock 来模拟请求返回值
- redis: 这里我试了下 miniredis 比较好用，基于 go 实现，无需真实的 redis server

也有一种方式在单测环境加入真实的db 和redis（比如 docker），然后单测读取测试环境的数据库来操作。
这样的好处是可以不使用各种 mock 库，直接操作真实的 mysql，测试代码写起来也更方便。

以下是一些单测相关的库：

- testing: 内置库
- github.com/stretchr/testify/assert: 用来做断言 assert 方便
- gomock(mockgen): 静态语言难以像动态语言直接属性替换，所以一般我们基于接口编写代码，然后可以生成接口 mock
- sqlmock: 如果依赖了数据库 mysql 等，可以使用 sqlmock 模拟数据库返回内容。（或者就在测试环境用真实的 mysql，测试完清理插入的测试数据)
- httpmock: 用来 mock 调 http 请求
- github.com/alicebob/miniredis 可以用来 mock redis，无需启动真实的 resdis server。试了下非常好用，也不用使用 mock 和真实的 redis 了。个人强烈推荐
- bouk/monkey: 通过替换函数指针的方式修改任意函数的实现，如果以上都无法满足需求，可以用这种比较 hack 的方式。可能需要禁止编译器内联优化 ``go test -gcflask=-l ./...``
- agiledragon/gomonkey: go 语言实现 monkey patch

目前比较推荐使用 assert 做断言，使用 gomonkey 用来 mock 函数/方法等。

参考：

- https://medium.com/@rosaniline/unit-testing-gorm-with-go-sqlmock-in-go-93cbce1f6b5b  (medium.com有阅读次数限制，隐身模式打开似乎就可以了)


Go 断点调试器dlv
---------------------------------------------------------------

.. code-block:: shell

   # 搜索函数，打断点，如果有同名函数的时候比较有用
   funcs FuncName

   # 打断点断点
   b main.main

   # 打印变量
   print val

   # go get -u github.com/derekparker/delve/cmd/dlv
   dlv debug main.go

   # 加上命令行参数
   # https://github.com/go-delve/delve/issues/562
   dlv debug ./cmd/unit-assignment-cli/main.go -- server

   # 如何调试 go 的 coredump 文件。对于一些很偶发的进程退出会比较难排查，可以利用 coredump 文件辅助排查问题：
   1. 调整ulimit关于core file size的设置，执行 ulimit -c unlimited 将core file size设成无限大小。
   2. 输出环境变量 export GOTRACEBACK=crash 使得golang进程知道需要产生cash时候的coredump文件。
   3. 分析 /usr/local/bin/dlv core ./app ./core_app
   4. 使用命令 goroutine goroutineid 和 bt 打印栈信息

   # dlv 常用命令：
   break main.go:7  # 在main.go 第 7 行加入断点
   break runtime.growslice # 函数处打断点
   continue # 继续执行运行到断点处
   disassemble # 插件对应的反汇编代码
   goroutines # 查看当前 goroutines
   stack(bt) # 查看调用栈信息
   regs  # 过regs命令可以查看全部的寄存器状态, 可以通过单步执行来观察寄存器的变化
   locals # 查看当前函数所有变量值

- https://yq.aliyun.com/articles/57578

Go 跨平台编译
---------------------------------------------------------------
用 Go 你可以选择自己喜欢的操作系统开发，并跨平台编译程序要发布平台的可执行程序即可。
Go 通过两个环境变量控制跨平台编译：

- GOOS: 代表要编译的目标操作系统，常见的有 Linux, Windows, Darwin 等
- GOARCH: 代表要编译的目标处理器架构，常见的有 386, AMD64, ARM64 等

比如现在在用 macOS AMD64 开发，但是想要编译出 Linux AMD64 的可执行程序，只需要执行：

``GOOS=linux GOARCH=amd64 go build main.go``

Go Debug 调试工具
---------------------------------------------------------------
- go-spew: 用来打印一些复杂结构方便调试 https://github.com/davecgh/go-spew
- dlv: 断点调试器

Go vs. Python
---------------------------------------------------------------
- http://govspy.peterbe.com/


Go Best practice(工程实践)
---------------------------------------------------------------
- https://draveness.me/golang-101 如何写出优雅的 golang 代码(好文推荐)
- https://github.com/golang/go/wiki/CodeReviewComments 作为 effective go 补充
- https://peter.bourgon.org/go-best-practices-2016/
- https://dave.cheney.net/practical-go/presentations/qcon-china.html
- https://golang.org/doc/effective_go.html
- https://talks.golang.org/2013/bestpractices.slide
- https://dave.cheney.net/practical-go
- https://github.com/codeship/go-best-practices
- https://github.com/uber-go/guide/blob/master/style.md   uber 的 go 规范

- https://12factor.net/zh_cn/
- https://go-proverbs.github.io go谚语，类似 python 之禅
- https://the-zen-of-go.netlify.com/ zen of go
- https://bluxte.net/musings/2018/04/10/go-good-bad-ugly/
- https://github.com/cristaloleg/go-advice
- https://dablelv.github.io/go-coding-advice/ Go 编码建议

Go 开发关键技术指南
---------------------------------------------------------------
- https://developer.aliyun.com/article/739836 Go 开发关键技术指南
- https://developer.aliyun.com/article/740696 Go 面向失败编程
- https://yq.aliyun.com/articles/741747 带着服务器编程金刚经走进 2020 年
- https://developer.aliyun.com/article/742169  Go 开发关键技术指南 | 敢问路在何方？

Go 常用命令
---------------------------------------------------------------

.. code-block:: shell

  # 获取 go 的 import 列表 (list import)
  # https://pmcgrath.net/how-to-get-golang-package-import-list
  go list -f '{{range $imp := .Imports}}{{printf "%s\n" $imp}}{{end}}' | sort
  go list -f '{{range $dep := .Deps}}{{printf "%s\n" $dep}}{{end}}' | xargs go list -f '{{if not .Standard}}{{.ImportPath}}{{end}}'

  # 清理模块缓存, GO111MODULE=on 以后，下载的模块内容会缓存在$GOPATH/pkg/mod 目录中： 使用以下命令可清空缓存：
  go clean --modcache

  # 跨平台编译
  `GOOS=linux GOARCH=amd64 go build main.go`

  # 强制重新构建(依赖包) 使用 -a。参考：http://c.biancheng.net/view/120.html
  go build -a main.go

  # go mod graph
  # 会显示出go.mod里需要的每个包,都依赖了哪些包。可以用这个工具可视化 https://github.com/PaulXu-cn/go-mod-graph-chart
  go get -u github.com/PaulXu-cn/go-mod-graph-chart/gmchart
  go mod graph | gmchart

  # remove any unused package
  go mod tidy -v


Go 数据结构与算法
---------------------------------------------------------------

- https://golangbyexample.com/all-data-structures-golang/
- https://github.com/emirpasic/gods
- https://github.com/Workiva/go-datastructures
- https://github.com/golang-collections/go-datastructures

博客：

- https://zhuanlan.zhihu.com/p/22803609 redigo demo
- https://blog.biezhi.me/2018/10/load-config-with-viper.html viper 解析配置

Go 底层实现(源码)
---------------------------------------------------------------
- https://draveness.me/golang/concurrency/golang-context.html
- https://github.com/tiancaiamao/go-internals/tree/master/zh
- https://zhuanlan.zhihu.com/p/80853548 深度解密Go语言之 scheduler
- https://github.com/cch123/golang-notes
- https://draveness.me/golang/  Go 语言设计与实现

Go Profiler
---------------------------------------------------------------
- pprof
- github.com/uber/go-troch: Flame graph profiler for Go programs，火焰图工具，配合压测看性能瓶颈
- https://cizixs.com/2017/09/11/profiling-golang-program/
- https://software.intel.com/en-us/blogs/2014/05/10/debugging-performance-issues-in-go-programs
- https://github.com/wolfogre/go-pprof-practice 实战教程

Go 性能优化
---------------------------------------------------------------
- https://github.com/dgryski/go-perfbook
- https://dave.cheney.net/high-performance-go-workshop/dotgo-paris.html
- https://stephen.sh/posts/quick-go-performance-improvements
- https://mp.weixin.qq.com/s/ogtRE_LbllN2Tla97LnFrQ
- https://zhuanlan.zhihu.com/p/482547957 Go 高性能编程技法
- https://geektutu.com/post/high-performance-go.html 《Go 语言高性能编程》

Goroutines
---------------------------------------------------------------
- https://medium.com/@vigneshsk/how-to-write-high-performance-code-in-golang-using-go-routines-227edf979c3c
- https://udhos.github.io/golang-concurrency-tricks/

Go 内存泄露(memory leak)
---------------------------------------------------------------
- https://go101.org/article/memory-leaking.html
- https://colobu.com/2019/08/28/go-memory-leak-i-dont-think-so/

Go 反射
---------------------------------------------------------------
- https://segmentfault.com/a/1190000016230264 Go Reflect 高级实践

Go 网络编程
---------------------------------------------------------------
- https://tumregels.github.io/Network-Programming-with-Go/  一本 go 网络编程入门在线电子书

Go 操作消息队列
---------------------------------------------------------------
- https://juejin.cn/post/6999263126713696293 Golang中如何正确的使用sarama包操作Kafka？

Go 并发模式
---------------------------------------------------------------
- https://blog.golang.org/pipelines

Go 位操作
---------------------------------------------------------------
- https://learnku.com/go/t/23460/bit-operation-of-go

Go 缺陷
---------------------------------------------------------------
- https://github.com/ksimka/go-is-not-good
- `50 Shades of Go: Traps, Gotchas, and Common Mistakes for New Golang Devs  <http://devs.cloudimmunity.com/gotchas-and-common-mistakes-in-go-golang/>`_
- https://bluxte.net/musings/2018/04/10/go-good-bad-ugly/

Go Leetcode
---------------------------------------------------------------
- https://github.com/austingebauer/go-leetcode
- https://books.halfrost.com/leetcode/ 一本 go leetcode 题解电子书

Go 面试题
---------------------------------------------------------------
- `Awesome Go Interview Questions and Answers <https://goquiz.github.io/>`_
- https://bytemode.github.io/interview/
- https://www.topgoer.cn/docs/gomianshiti/mianshiti

Go源码阅读
---------------------------------------------------------------
除了内置库之外，go 还有很多优秀的源码值得学习。建议用到的一些优秀的第三方库的源码都可以看一下，了解底层实现也方便排查问题。

- https://golang.design/under-the-hood//
- https://bytemode.github.io/reading/
- https://docs.kilvn.com/go-internals/ref2.html
- https://draveness.me/golang/docs/part1-prerequisite/ch01-prepare/golang-debug/

.. image:: ../_image/goweb/gocode阅读.png
