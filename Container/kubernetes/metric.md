## k8s监控系统

### Prometheus项目
  * Prometheus架构图![prometheus架构图](../images/prometheus_arch.png)

### Metrics监控数据源
1. 宿主机的监控数据，通过NodeExporter

2. 核心组件(API-Server/Kubelet等)的监控数据，通过组件的/metrics API暴露
  * controller的工作队列长度
  * 请求的QPS和延迟数据等

3. Kubernetes核心监控数据
  * 被监控对象是Node/Pod/Service等对象
  * kubelet内置的cAdvisor服务收集容器的metrics
  * 核心监控数据通过Metric Merver(通过API Aggregator方式)

### 参考资料
* [Kubernetes监控体系](https://time.geekbang.org/column/article/72281)  