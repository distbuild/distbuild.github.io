# Remote Execution API



## 概述

distbuild 兼容符合[Remote Execution API](https://github.com/bazelbuild/remote-apis) 标准（"REAPI"）的远程缓存和远程执行服务器。REAPI 协议由多个不同的服务器和客户端项目支持，包括 Bazel。

REAPI 服务器实现几个相关但不同的服务：

- "content-addressable storage"内容可寻址存储服务，用于存储以数据哈希值为键的数据（也称为"CAS"）。

- "action cache service"操作缓存服务，将进程执行映射到其结果
- "execution service"执行服务，通过使用内容可寻址存储服务获取输入并存储运行这些进程的输出来执行进程。

远程缓存服务器实现 CAS 和操作缓存服务。远程执行服务器实现所有三个服务。

REAPI 模型包含"instance"实例概念。实例是 CAS 和/或执行服务的独特部署，被赋予特定名称。所有 REAPI 操作都向服务器发送实例名称，因此单个网络端点可以支持多个 REAPI 部署。



## 测试

[remote-apis-testing project](https://gitlab.com/remote-apis-testing/remote-apis-testing) 维护各种 REAPI 服务器和客户端实现的兼容性测试套件。



## 参考

- https://www.pantsbuild.org/docs/remote-caching-execution
