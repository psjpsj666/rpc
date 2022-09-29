# rpc远程调用网络通信框架
支持远程调用部署在不同机器上的函数/方法。用框架
1. 使用Protobuf实现了RPC请求和响应的序列化和反序列化；
2. 基于muduo网络库实现了RPC请求和响应的发送和接收；
3. 使用Zookeeper作为注册中心，保证RPC服务的统一配置管理；
4. 实现了异步日志系统，记录RPC框架的运行状况。

rpc调用过程：
![image](https://user-images.githubusercontent.com/68554367/192940426-3f19b5c8-d2dc-4516-821b-1ffc4ada0aa7.png)

黄色部分：设计rpc方法参数的打包和解析，也就是数据的序列化和反序列化，使用Protobuf。<\br>
绿色部分：网络部分，包括寻找rpc服务主机，发起rpc调用请求和响应rpc调用结果，使用muduo网络库和zookeeper服务配置中心（专门做服务发现）。<\br>

源码结构：
bin：可执行文件<\br>
build：项目编译文件<\br>
lib：项目库文件<\br>
src：源文件<\br>
test：测试代码<\br>
example：框架代码使用范例<\br>
CMakeLists.txt：顶层的cmake文件<\br>
README.md：项目自述文件<\br>
autobuild.sh：一键编译脚本<\br>

