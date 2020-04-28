# 网络连接

Ouster 激光雷达使用以太网进行通讯，利用 UDP 进行激光点云和 IMU 的数据传输，利用 TCP 对雷达进行状态查询和配置，也提供 HTTP API （详情见用户手册）可以查询雷达和对一些功能进行设置。

## 查找雷达 IPv4 地址

无论是 UDP 还是 TCP，在和雷达通讯前都需要为雷达分配一个本机网络下的可用IPv4地址。下面是不同系统寻找雷达IP地址的方法：

### Ubuntu - avahi-browse

Ouster 雷达在DNS中的类型为 `_roger._tcp` 在命令行中输入 `avahi-browse -lr _roger._tcp` 可以搜索到雷达在网络中的信息：

![avahi-browse command](imgs/avahi-browse)

其中 *hostname* 为该雷达的域名可以通过过任一浏览器输入地址 http://hostname (例：http://os1-991946000317.local) 访问雷达网页接口。

*address* 为该雷达 IPv4 地址，浏览器可以直接输入该地址访问网页接口。



### MAC - dns-sd


### Windows - 


## 查找本机网络端口 IPv4 地址

只有在得知目的地IP地址后，激光雷达才开始讲数据通过 UDP 的形式发送到改地址。下面是不同系统中寻找本机网络端口 IPv4 地址的方法：

### Ubuntu/Mac - ifconfig/ip a

### Windows - ipconfig

## 单播/广播/组播

可以通过 TCP 命令 `sfsaf` 对雷达 UDP 通讯的目标地址进行设置。设置后，雷达将在启动后主动将激光雷达数据和IMU数据发送到该地址，以此实现数据单播/广播/组播功能。示例如下:

```

我是代码
我是代码
我是代码

```