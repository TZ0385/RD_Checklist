.. _工程化能力:

工程化能力
~~~~~~~~~~~~~~

研发能力
~~~~~~~~~~

瀑布模型
""""""""

* 需求 -> 需求分析 -> 设计 -> 开发 -> 测试 -> 上线 -> 运维/运营

需求分析能力
""""""""""""

* 给你一个需求，如何给出一个优美的执行思路——方法论
* 这个能力非常非常非常的关键

调试能力
""""""""

* 只要定位出，就没有解决不了的 Bugs
* 肉眼看到的都是假象

  + 一定要专业的工具与经验配合

* Bugs 在哪出现，最终就在哪进行真实模拟调试
* 缩小范围

  + 构建自己的测试样例

    - 排除网络复杂未知情况

  + 关联模块一个个排除
  + Python 单步调试

    - import pdb; pdb.set_trace()
    - 在需要单步调试的地方加上面这句，运行程序后中断在此，然后 h 查看指令进行一步步细细调试

  + 粗暴调试：print

敏捷思想
""""""""

* 快速迭代
* 任务拆细
* v1 原则：定义好 v1 的目标，快速完成 v1 为优先
* 习惯 WiKi 记录，利于沉淀与分享

编码环境
~~~~~~~~~~
* tmux/screen
* Vim
* Markdown
* zsh + oh-my-zsh
* fish 也值得一试
* Python3
    + IPython
    + pip
    + venv
    + Django
    + 其它Web框架
      + web.py
      + Flask
      + Tornado

* Golang
    + [Gin](https://github.com/gin-gonic/gin)
    + [Beego](https://github.com/astaxie/beego) 
    + gorm(ORM)

* Node.js
* Ubuntu/Debian/Fedora/Kali
* 版本控制
  + Git
  + GitLab
* Nginx + uWSGI
* 让你的电脑默认操作系统就是 Mac/Linux...

前端
~~~~

书
""""

* 《JavaScript DOM 编程艺术》

了解 DOM
""""""""

* 这同样是搞好前端安全的必要基础

库
""""

* jQuery

  * 优秀的插件应该体验一遍，并做些尝试
  * 官方文档得过一遍

* D3.js
* ECharts

  + 来自百度

* Google API
* ZoomEye Map 组件

  + ZoomEye 团队自己基于开源的打造

* Vue.js

  + 国内开源的渐进式 JavaScript 框架

* React

  + Facebook 出品的前端渲染框架

  + Antd  蚂蚁集体开源的前端组件库

* Bootstrap

  + 应该使用一遍

爬虫进阶
~~~~~~~~

* 代理池

  + 爬虫「稳定」需要

* 网络请求

  + wget/curl
  + urllib3/httplib2/requests
  + Scrapy

* 验证码破解

  + pytesser

调度
~~~~

* crontab 是最原生的定时调度
* 基于 Redis 实现的分布式调度
* 基于 RPyC 实现的分布式调度
* Celery/Gearman 等调度框架

并发
~~~~

* 线程池

  + 进程内优美的并发方案

* 协程

  + 进程内另一种优美的并发方案
  + gevent

* 多进程

  + os.fork
  + multiprocessing

算法
""""

* 快排
* 二分
* 分词
* 贝叶斯
* 神经元
* 遗传算法
* 聚类/分类
* ...

正则表达式
""""""""""""""
* 调试工具

  + Kodos
  + RegexBuddy

    - 支持多种语言
    - 支持调试优化

  * http://www.regexper.com/

    + 正则图解

  * https://regex101.com

    + regex101: build, test, and debug regex

* 正则表达式30分钟入门教程：http://deerchao.net/tutorials/regex/regex.htm
* Python正则表达式操作指南：http://wiki.ubuntu.org.cn/Python%E6%AD%A3%E5%88%99%E8%A1%A8%E8%BE%BE%E5%BC%8F%E6%93%8D%E4%BD%9C%E6%8C%87%E5%8D%97
* 《精通正则表达式》

数据结构
~~~~~~~~

* JSON
* cPickle
* protobuf

数据库
~~~~~~
* Postgresql
* MySQL
* MongoDB
* SQLite
* Redis
* ElasticSearch

大数据处理
~~~~~~~~~~

* Hive
* Spark
* ELK

  + ElasticSearch
  + Logstash
  + Kibana

DevOps
~~~~~~

* SSH 证书
* Fabric
* SaltStack
* Puppet
* pssh/dsh
* 运维进阶

  + 运维工程师必须掌握的基础技能有哪些？
  + http://www.zhihu.com/question/23665108/answer/25299881

调试
~~~~

* pdb
* gdb
* windbg
* logging
* Sentry
* strace/ltrace
* lsof
* 性能

  + Python 内

    - timeit
    - cProfile
    - Python性能分析指南：http://www.oschina.net/translate/python-performance-analysis

  + Python 外

    - top/htop/free/iostat/vmstat/ifconfig/iftop...

持续集成
~~~~~~~~

* 自测试

  + nose

* Jenkins


协作
~~~~

* 立会
* 微信
* Slack
* 类似 Trello 的在线协同平台

AI 应用
~~~~~~~~~~

* 让 AI 带你入门新领域

* 为 AI 添加新数据

  - RAG
  - Embeddings
  - 原始模型微调 Fine-tuning
  - ...

* 为 AI 添加新能力

  - 在线数据获取
  - 方法调用 function calling
  - 代码执行环境 code interpreter
  - ...

* 让 AI 参与自动化

  - 数据分级分类
  - 关键信息提取
  - 样本数据生成
  - ...

* 注意数据安全

设计思想
~~~~~~~~~~

* 人人都是架构师：具备架构思想是一件多酷的事
* 实战出真知
* 如何设计

  + 松耦合、紧内聚
  + 单元与单元属性
  + 生产者与消费者
  + 结构

    - 队列
    - LRU

  + 分布式

    - 存储
    - 计算

  + 资源考虑

    - CPU
    - 内存
    - 带宽

  + 粗暴美学/暴力美学

    - 大数据，先考虑 run it，然后才能知道规律在哪
    - “run it 优先”能快速打通整体，洞察问题
    - “run it 优先”能摆脱细节（繁枝末节）的束缚
    - “run it 优先”能快速迭代出伟大的 v1

  + 一个字总结

    - 美
