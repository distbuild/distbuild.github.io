# 介绍

distbuild 在运行它的系统上本地执行进程，并且也在本地缓存这些进程的结果。除了这种"local execution"操作模式外，distbuild 还支持两种分布式操作模式：

- "Remote caching"：distbuild 将本地进程执行的结果存储在远程缓存中，并且也从该远程缓存中消费结果

- "Remote execution"：distbuild 将进程的执行卸载到远程服务器（并从该远程服务器消费缓存的结果）

distbuild 通过使用"Remote Execution API"与远程缓存或远程执行服务器进行通信来实现这一点。
