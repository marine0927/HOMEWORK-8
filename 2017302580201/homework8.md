# 网络及分布式第八次作业

2017302580201-贺谷穗子

### 一、课本第四章习题选做三道

> P11.考虑一个具有前缀12& 119. 40. 128/26的子网。给出能被分配给该网络的一个IP地址（形式为 xxx. XXX. xxx. xxx）的例子o假定一个ISP拥有形式为12& 119. 40. 64/26的地址块。假定它要从该地 址块生成4个子网，每块具有相同数量的IP地址。这4个子网（形式为a. b. c. d/x）的前缀是什么?

128.119.40.133

四个子网的前缀是： 128.119.40.64/28, 128.119.40.80/28, 128.119.40.96/28, 128.119.40.112/28



> P16.考虑在图4-25中建立的网络。假定ISP现在为路由器分配地址24.34.112.235,家庭网络的网络地 址是 192. 16& 1/24。 
>
> a.在家庭网络中为所有接口分配地址。 
>
> b.假定每台主机具有两个进行中的TCP连接，所有都是针对主机128.119. 40. 86的80端口的。在 NAT转换表中提供6个对应表项。

a.192.168.1.1;192.168.1.2;192.168.1.3;192.168.1.4

b.

|        WAN         |       LAN        |
| :----------------: | :--------------: |
| 24.34.112.235,4000 | 192.168.1.1,3345 |
| 24.34.112.235,4001 | 192.168.1.1,3346 |
| 24.34.112.235,4002 | 192.168.1.2,3445 |
| 24.34.112.235,4003 | 192.168.1.2,3446 |
| 24.34.112.235,4004 | 192.168.1.3,3545 |
| 24.34.112.235,4005 | 192.168.1.3,3546 |




> P20.再次考虑显示在图4-30中的SDN OpenFlow网络。假定在s2对于来自主机h3或h4的数据报的期望 转发行为如下： 
>
> • 任何来自主机h3并且发往主机hl、h2、h5或h6的数据报应当在网络中以顺时针方向转发。
>
> • 任何来自主机h4并且发往主机hl、h2、h5或h6的数据报应当在网络中以逆时针方向转发。
>
> 详述实现这种转发行为的s2中的流表项。

解答如下表格

|                 匹配                 |    动作    |
| :----------------------------------: | :--------: |
| Ingress Port = 3; IP Dst = 10.1.* .* | Forward(2) |
|   Ingress Port=3;IP Dst=10.3 .* .*   | Forward(2) |
|   Ingress Port=4;IP Dst=10.1.* . *   | Forward(1) |
|   Ingress Port=4;IP Dst=10.3.* .*    | Forward(1) |

