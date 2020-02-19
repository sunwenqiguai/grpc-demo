##gRPC是什么？
在 gRPC 里客户端应用可以像调用本地对象一样直接调用另一台不同的机器上服务端应用的方法，使得您能够更容易地创建分布式应用和服务。与许多 RPC 系统类似，gRPC 也是基于以下理念：定义一个服务，指定其能够被远程调用的方法（包含参数和返回类型）。在服务端实现这个接口，并运行一个 gRPC 服务器来处理客户端调用。在客户端拥有一个存根能够像服务端一样的方法。

####gRPC具有以下特点：

（1）基于 HTTP/2， 继而提供了连接多路复用、Body 和 Header 压缩等机制。可以节省带宽、降低TCP链接次数、节省CPU使用和延长电池寿命等。

（2）支持主流开发语言（C, C++, Python, PHP, Ruby, NodeJS, C#, Objective-C、Golang、Java）

（3）IDL (Interface Definition Language) 层使用了 Protocol Buffers, 非常适合团队的接口设计
##为什么使用gRPC?
1. 性能   
   (1) ProtoBuf它以高效的二进制方式存储，序列化性能高；   
      序列化后体积相比 Json 和 XML 很小，适合网络传输   
   (2) HTTP/2
2. gRPC 接口规范   
   (1) 强类型，也就是说，写的时候，编译器会帮你检查很多东西，这样就不会留着在运行时报错，正所谓动态一时爽，重构火葬场。 从我个人体验来说，强类型的确能够帮助减少很多bug。   
   (2) 自动生成SDK。当你对接很多RESTful API时，你会发现，每个语言都要封装一份SDK，否则就只能大家都裸写JSON，这是一件很蛋疼的 重复劳动的事情，gRPC解决了这个痛点(其它RPC大多也解决了)。
   
3. 流的支持

##gRPC缺点？
1. 调试不方便
2. 负载均衡   
Kubernetes负载平衡器（用于HTTP服务）在gRPC上不能很好地工作。基本上，gRCP需要应用程序级的负载平衡，而不是TCP连接级的负载平衡。为了解决这个问题，我们按照本教程的指导建立了Linkerd：Kubernetes无痛作gRPC负载平衡。
https://kubernetes.io/blog/2018/11/07/grpc-load-balancing-on-kubernetes-without-tears/

##gRPC、thrift和Dubbo对比？
