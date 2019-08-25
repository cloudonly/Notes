### Kubernetes in Action 学习笔记

#### Pod
* Pod访问内部Pod
* Pod访问外部服务
* Pod应用暴露给外部访问(NodePort/Ingress/LoadBalance)

#### Service
* ClusterIP
* NodePort & LoadBalance
* Ingress
* Headless Service
* Endpoint

#### Volume
* Volume
* PV & PVC
* StorageClass

#### Deployment 
 
#### Stateful

#### Kubernets 机制

#### RBAC
* 认证--ServiceAccount
* 授权--Role/RoleBinding/ClusterRole/ClusterRoleBinding

#### 资源管理
* resource request/limit
* QoS--BestEffort/Burstable/Guaranteed
* LimitRange
* ResourceQuota
* 监控资源使用量

#### AutoScaling
* HPA(HorizontalPodAutoscaler)
* Cluster Autoscaler

#### Advanced Scheduler
* Taint & Toleration
* Node Affinity
* PodAffinity & PodAntiAffinity