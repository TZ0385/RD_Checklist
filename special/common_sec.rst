.. _通用安全能力/概念:

通用安全能力/概念
=========================

安全研究员的基本功，决定了研究能力的下限，这些即可以是实用于其他领域的工具方法，又可以作为单独的研究方向。

密码学
===========

* 对称加密

  - AES
  - DES
  - 3DES
  - SM1 / SM4
  - ...

* 非对称加密

  - RSA
  - ECC
  - SM2
  - ...

* Hash算法

  - MD5
  - SHA1
  - SHA256
  - SM3
  - NTLM hash
  - ...

* 混合加密方案/应用

  - SSL/TLS
  - SSH
  - IPsec
  - ...

* 密码爆破

社会工程学
===============

* 信息获取

  + 社交工程侦查
  + 垃圾搜寻
  + 个人疏忽泄露
  + ...

* 行为诱导

  + 钓鱼，各种各样的钓鱼
  + 伪装利用同情心、亲和力或权威
  + 群体压力
  + 尾随捎带

大家在网络空间也要记得保护好自己

网络发现和管理
==================

* 公网设备发现

  - 网络空间测绘引擎 ZoomEye

* 内网拓扑分析

* 梯子/内网穿透

  - 机场
  - v2ray
  - wireguard
  - frp转发
  - ssh隧道
  - 还有很多隧道用法
  - ...

如何给浏览器、shell、docker等环境配置代理就不多赘述了

抓包和流量分析
===================

curl
----------

* 加-v参数后理解HTTP协议最佳工具之一，不止于此，还支持很多其它协议。。。
* 很不错的教程： https://www.ruanyifeng.com/blog/2019/09/curl-reference.html
* 更多的技巧，man一下吧

BurpSuite
---------------

* 抓包与各种调试
* 拦截修改
* 重放功能
* 编码解码/POST 提交
* kali默认自带社区版，够你用了


Mitmproxy
--------------

* 中间人代理工具，可以用来拦截、修改、保存 HTTP/HTTPS 请求


Wireshark/tcpdump
---------------------

* 各种强大的过滤器语法
* 各种硬件接口与协议的支持
* 可以配合 curl 进行协议分析学习

虚拟化与隔离
=================
这里不讨论广义上的虚拟化技术，只是在安全研究中经常会接触到的虚拟化概念

沙箱
-------

其核心目的是提供隔离机制，使程序可以在一个受限的环境中运行，以减少潜在的安全风险。

所以这是一个可大可小的概念，它可以是浏览器中的脚本解析器，也可以是智能手机为每个app提供的运行环境，
还可以是测试来源不明的程序的虚拟机，甚至是一台断了网的电脑，都可以被称作沙箱。

容器
--------

容器共享宿主机的操作系统内核，但每个容器之间相互隔离。

可以理解为操作系统虚拟化，容器将应用及其依赖环境打包在一起，创建一个可以独立运行的“轻量级”虚拟系统。
通常使用 Linux 内核的命名空间和控制组等特性来实现资源隔离，因此容器的安全性依赖于宿主机的内核与具体配置。

虚拟机
----------

软件模拟一个完整的硬件环境，每个虚拟机都有自己的操作系统。

可以理解为硬件虚拟化，软件模拟的硬件环境，可以与宿主机的硬件架构不同，因此兼容性和隔离性都更好。
但是虚拟机的资源消耗大，每次运行都需要加载整个操作系统，如果硬件架构不同，造成的开销会更大。

逆向工程
============

静态分析
------------
不执行程序代码，通过查看程序反编译的汇编代码、字节码或高级语言代码来判断程序的功能和结构

* IDA Pro 的基本使用

  + 修改变量类型
  + 搜索定位
  + 定义结构体
  + Patch
  + 编写idapython插件
  + ...

* 其他静态分析工具

  + Ghidra
  + Ninja
  + Radare2
  + objdump
  + jd-gui (java)
  + dnspy (.Net)
  + jadx (android dex)
  + ...

动态分析
------------
实际运行程序，通过调试或Hook等方式，来理解目标程序的工作机制

* 熟练掌握其中一个或多个调试工具

  + IDA Pro
  + WinDbg
  + x64dbg
  + GDB

    - GDB 的基本使用
    - .gdbinit 的基本使用，比如自定义一个GDB命令
    - 使用 python 开发 GDB 插件
    - GDB 的插件：Pwndbg / gef / peda / ...

恶意文件识别（与 免杀）
============================

* 恶意文件识别

  + 特征匹配
  + 行为分析

* 免杀手段

  + 加壳/加密 + 自定义loader
  + 运行环境检测
  + 隐蔽通信
  + 寄生合法软件
  + ...

* 加壳技术的发展

  1. 源码混淆、可执行文件压缩加密，运行前解密；
  2. 内存中解密重组文件并加载执行代码段，无文件落地；
  3. 根据可执行文件的结构，仅解密函数索引，按需解密并加载执行代码段；
  4. 指令转义，通过自定义的解释器执行等效代码，也就是虚拟机壳；

漏洞分析/挖掘
================

漏洞复现
--------------------

* 环境搭建

  - 对应版本
  - 对应功能组件与设置

* 触发漏洞
* 分析漏洞成因
* 开发漏洞利用

补丁对比
-------------------

* diff工具
* bindiff
* Beyond Compare
* ...

模糊测试
--------------------

模糊测试的目标类型
""""""""""""""""""""

* 文件格式
* 网络协议
* 脚本解析
* 系统调用
* ...

覆盖率导向的fuzz流程
""""""""""""""""""""""

* 收集语料库素材
* 代码插桩

  + 源代码插桩

    - gcc
    - clang

  + 静态二进制插桩

    - dyninst

  + 动态运行时插桩

    - aflpin
    - Qemu 模拟
    - DynamoRIO

* 变异算法

  + 随机变异
  + 语法/模版指导变异
  + 协议/API调用序列变异
  + ...
  
* 异常捕获

  + 异常退出
  + ASAN检测内存异常
  + ...
  
* 覆盖率检测

  + afl-cov
  + gcov, lcov

主流Fuzz框架
""""""""""""""""

* AFL++
* libfuzzer
* honggfuzz
* boofuzz
* syzkaller
* fuzzilli
* ...

代码审计
-------------
在对漏洞类型的理解上，结合源码或逆向工程对软件进行漏洞挖掘

代码审计思路
""""""""""""""""""""""""""

* 理解 source to sink
* 从数据输入/生成处开始，跟踪数据传递过程是否有逻辑错误，判断是否会流入敏感函数；
* 从程序中的敏感函数开始，逆向倒推数据来源是否可控，是否经过充分检查与过滤；

自动化静态代码审计框架
""""""""""""""""""""""""""

* CodeQL
* Tai-e
* Fortify
* FindBugs
* Cppcheck
* ...

>_