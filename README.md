#gRPC是什么？
在 gRPC 里客户端应用可以像调用本地对象一样直接调用另一台不同的机器上服务端应用的方法，使得您能够更容易地创建分布式应用和服务。与许多 RPC 系统类似，gRPC 也是基于以下理念：定义一个服务，指定其能够被远程调用的方法（包含参数和返回类型）。在服务端实现这个接口，并运行一个 gRPC 服务器来处理客户端调用。在客户端拥有一个存根能够像服务端一样的方法。

gRPC具有以下特点：

（1）基于 HTTP/2， 继而提供了连接多路复用、Body 和 Header 压缩等机制。可以节省带宽、降低TCP链接次数、节省CPU使用和延长电池寿命等。

（2）支持主流开发语言（C, C++, Python, PHP, Ruby, NodeJS, C#, Objective-C、Golang、Java）

（3）IDL (Interface Definition Language) 层使用了 Protocol Buffers, 非常适合团队的接口设计