.. _专业安全能力:

专业安全能力
==================

正所谓术业有专攻，在自己的专业领域要有深度有沉淀。So many things to hack, such little time to work.

Web安全
==================

Web 常见漏洞类型
---------------------

* 注入漏洞

  + SQL注入
  + XXE
  + 命令注入/代码注入
  + ...

* XSS
* CSRF
* SSRF
* 反序列化漏洞
* 任意文件上传
* ...

Web 审计
---------------------
代码审计需要编程语言的基础，结合对漏洞类型的理解来进行，尽管Web后台/中间件使用了不同的语言与框架，但关注的点是共通的

* http 请求中的参数获取，比如POST数据
* 文件操作
* 数据库接口
* 系统命令执行
* Session管理
* 序列化与反序列化
* 框架配置读取/插件加载
* 编程语言特性，像是类继承/重载、字符串对比、include文件包含等等
* ...

二进制安全
==================

二进制基础
---------------------
除了必修其他基础每多学一个，可以增加一倍二进制能力

* 汇编语言（必修）

  + x86/x64
  + mips/mips64
  + arm/aarch64
  + ...

* 计算机网络（重要）
* 操作系统（搞内核安全的基础）
* 数据结构、编译原理、计算机组成原理

二进制漏洞类型
""""""""""""""""""

* 栈溢出
* 堆溢出
* 整数溢出
* UAF
* double free
* 空指针引用
* 格式化字符串
* 类型混淆
* ...

二进制入门书籍推荐
""""""""""""""""""

* 《汇编语言》
* 《深入理解Windows操作系统》
* 《Windows驱动开发技术详解》
* 《深入理解Linux内核架构》
* 《CPU眼里的C/C++》
* 《0day安全：软件漏洞分析技术》
* 《漏洞战争：软件漏洞分析精要》
* 《Exploit编写系列教程》

Windows
---------------------

Windows 开发
""""""""""""""""""

* Windows api 官方文档

  + `官方参考链接 <https://docs.microsoft.com/en-us/windows/win32/apiindex/windows-api-list>`_

* Windows api hook 的原理与应用
* Windows 驱动开发

  + `Windows 内核模式驱动程序设计指南 <https://learn.microsoft.com/zh-cn/windows-hardware/drivers/kernel/>`_
  + `Windows 进程间通信基础 <https://learn.microsoft.com/zh-cn/windows/win32/ipc/interprocess-communications#using-rpc-for-ipc>`_
  + `Windows 内核驱动示例 <https://github.com/microsoft/Windows-driver-samples>`_

* Windows 下通信机制

  + 通过 RPC 进行通信
  + 通过 COM 进行通信
  + 通过 管道 进行通信
  + 通过 剪贴板 进行通信

Windows 分析调试
""""""""""""""""""

* `Windbg 官方文档 <https://learn.microsoft.com/zh-cn/windows-hardware/drivers/debugger/getting-started-with-windbg>`_

* 符号表获取

  + `Microsoft 公共符号服务器 <https://learn.microsoft.com/zh-cn/windows-hardware/drivers/debugger/microsoft-public-symbols>`_

* 双机调试

  + 常用于内核调试

Windows 漏洞缓解措施
""""""""""""""""""""""

* 数据执行保护 DEP
* 地址空间随机化 ASLR
* 控制流保护 CFG
* 管理模式执行保护 SMEP
* 页表随机化 PageTable Randomization
* 任意代码保护 ACG
* 返回流保护 RFG
* ...

Linux
--------------------

Linux 常见漏洞缓解措施
"""""""""""""""""""""""""

* 栈保护 stack canary
* 禁止执行内存 NX (同 windows 中的DEP)
* 地址空间随机化 ASLR
* 位置无关可执行文件 PIE
* 只读重定位 RELRO
* 内核地址空间随机化 KASLR
* 内核页表隔离 KPTI
* 管理模式限制访问/执行 SMAP/SMEP
* ...

移动安全
=================

关于测试机
----------------------
可以找模拟器临时用，推荐有条件的还是买一个测试机（无论如何，不要用主力机搞测试！）
这里给出一些关键词，具体Root方案和环境配置要根据实际情况来

* 开发人员选项、USB调试、OEM解锁，adb / fastboot
* 刷机/获取Root：twrp、Magisk、KernelSU ...
* Hook工具/框架：frida、Xposed（不维护以后又出现了EdXposed、LSPosed ...）
* 抓包相关：了解一下Android 7之后App默认不信任用户CA证书的https抓包方案
* 脱壳、Hook、调试工具，如何隐藏Root和Hook环境

App 安全
----------------------

* 静态：硬编码的业务域名与API格式、用户数据存储/备份 ...
* 动态：代码侧载（插件/热补丁） 、Content Provider/Service接口处理、deeplink注册、各种媒体解析器 ...
* 通信：SSL证书绑定、敏感数据加解密

Android 系统的结构层次
------------------------
当前的移动操作系统其实是脱胎于PC操作系统（二进制安全），很多攻击面和漏洞会相互影响，还是要根据对应的系统层次来看

* 应用层

  - App 安全

* 应用框架层

  - 前端框架、系统组件、服务以及权限管理

* 系统运行库层

  - libc
  - 媒体渲染
  - 数据库引擎
  - ...

* 硬件抽象层

* Linux 内核层

  - Binder 机制
  - 蓝牙协议栈
  - ...

IoT安全
================

IoT安全涉及范围广泛，包括但不限于网络基础设施（如路由器和交换机）、工业控制系统、智能家居设备、无人机以及车联网等。

IoT安全研究基础
--------------------

* 协议分析，OSI七层网络模型
* 嵌入式 Linux 系统方面知识
* 实时系统 （VxWorks / FreeRTOS等）
* 汇编语言 （Arm / mips / Risc-V）
* 交叉编译环境
* JTAG 调试接口规范
* ...

IoT相关工具
-------------------

* Binwalk
* IDA Pro
* Qemu （qemu-system / qemu-user-static）
* gdb / gdbserver
* busybox
* 无线电硬件

  - RTL-SDR
  - HackRF One
  - BladeRF
  - ...

* UART 串口调试器
* JTAG 硬件调试器
* ...

无线电链路协议
----------------

* 近距离无线通信

  - NFC
  - RFID
  - 433/915 MHz频段遥控信号

* 局域无线通信

  - Wifi
  - 蓝牙/低功耗蓝牙协议
  - ZigBee
  - Lora
  - ...

* 基站通信

  - GSM
  - 3G
  - 4G/LTE
  - 5G
  - ...

* 卫星通信

  - GPS 定位
  - 卫星电视
  - ...

通讯协议
------------

* 工控协议

  - S7Common
  - Modbus
  - ...

* 无人机相关

  - MAVLink
  - ...

* 车联网相关

  - DSRC
  - LTE-V2X
  - ...

* 云服务通信协议

  - MQTT/MQTTX
  - CoAP
  - ...

硬件安全
------------

* 安全启动与完整性保护
* 硬件调试接口
* flash 加密
* 硬件逆向工程
* 处理器架构漏洞
* 硬件侧信道问题

浏览器安全
===============

当前常见浏览器内核
-----------------------

* Chrome 

  - Chromium/Blink内核
  - v8引擎

* Safari

  - WebKit内核
  - JavaScriptCore

* Firefox

  - Gecko内核
  - SpiderMonkey

* Internet Explorer (已弃用)

  - Trident内核
  - Chakra

浏览器漏洞分类
-----------------------

* 解析器漏洞
* DOM 漏洞
* JS 引擎漏洞 (包括WASM)
* 同源策略绕过(SOP-bypass)/通用跨站脚本 UXSS
* ...

浏览器常见漏洞缓解措施
-----------------------

* 站点隔离
* 系统调用限制 / 基于虚拟化的沙箱
* 堆隔离 Isolated heap
* 延迟释放 Delayed free
* 堆原数据保护 Heap metadata protection
* 跨域隔离环境 COOP/COEP 
* ...

区块链安全
================

用户安全参考
----------------------

* `区块链黑暗森林手册 <https://github.com/slowmist/Blockchain-dark-forest-selfguard-handbook/>`_
* `加密资产安全解决方案 <https://github.com/slowmist/cryptocurrency-security>`_

开发安全参考
----------------------

* `Web3 项目安全实践要求 <https://github.com/slowmist/Web3-Project-Security-Practice-Requirements>`_

安全研究与审计
----------------------

* `慢雾智能合约审计技能树 <https://github.com/slowmist/SlowMist-Learning-Roadmap-for-Becoming-a-Smart-Contract-Auditor>`_
* `基于区块链的加密货币安全审计指南 <https://github.com/slowmist/Cryptocurrency-Security-Audit-Guide/>`_


AI 安全
=============

* 使用 AI 为现有的网络安全项目提供辅助，这一项应该放在本技能表的“工程化能力”章节来谈

* 针对 AI 模型或训练过程的安全问题，可以了解一下“数据污染”、“数据后门”和“对抗性模型”等，由此引发的安全问题通常为以下三类：

  + 模型误判

  + 算力消耗、拒绝服务攻击

  + 训练数据泄露

* 针对 AI 部署和应用构建的安全问题

  通过提示词注入（Prompt Injection）能够让我们绕过应用的系统提示词（System Prompt）的限制，例如

  + 绕过 AI 对话应用的道德限制

  + 修改 AI 翻译应用的输出结果

  + 绕过 AI 驱动的内容审查机制

  添加了更多功能的 AI 应用，提示词注入也能够使我们接触到应用中“传统安全”的那部分，例如

  + 在线信息获取，该功能会从指定 URL 获取信息，或是启动一个爬虫

  + Function Call功能，能够调用预设 API 接口

  + Code Interpreter功能，会创建一个隔离的容器环境，通常是docker

当下 AI 行业正在向着大模型、多模态的方向发展，基于 AI 的应用也在探索着各种新的可能，这将不断带来新的安全性的问题与讨论

作为初学还是有必要从内部了解 AI 大模型的构成与运行机制，推荐读一下《这就是ChatGPT》

持续学习，保持关注 `Seebug Paper AI安全 <https://paper.seebug.org/category/AIsecurity/>`_

>_