## Kubernetes网络

### Understanding kubernetes networking系列

* [pods](https://medium.com/google-cloud/understanding-kubernetes-networking-pods-7117dd28727)
* [services](https://medium.com/google-cloud/understanding-kubernetes-networking-services-f0cb48e4cc82)
* [ingress](https://medium.com/google-cloud/understanding-kubernetes-networking-ingress-1bc341c84078)

### 容器跨主机通信

#### Flannel
1. UDP -- (IP in UDP)
  * 三层Overlay网络，发端IP包封装在UDP中，接端解封装得到IP包
  * UDP方式跨主机通信原理![udp跨主机通信](../images/flannel_udp.png)
  * TUN设备示意图![TUN设备示意图](../images/flannel_udp_flow.png)

2. VXLAN -- (MAC in UDP)
  * 二层的Overlay网络
  * VTEP flannel.1打通二层“隧道”网络
  * VXLAN方式跨主机通信原理![vxlan跨主机通信](../images/flannel_vxlan.png)
  
3. host-gw
  * 三层网络
  * host-gw方式跨主机通信原理![host-gw跨主机通信](../images/flannel_hostgw.png)
  * 将每个Flannel子网的“下一跳”设置为子网对应的宿主机IP地址
  * Flanneld可以watch Etcd中子网和主机的信息变化，更新路由表
  * 要求宿主机网络二层连通
  
#### Calico

1. Calico工作原理![calico工作原理](../images/calico_1.png)

2. Calico IPIP模式工作原理![calico ipip模式工作原理](../images/calico_ipip.png)