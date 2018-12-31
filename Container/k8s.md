### Kubernetes

##### Pod Probe(探针)
* Liveliness
  
* Readiness

LivelinessProbe也称存活探针，检查容器是否正常运行即存活与否

ReadinessProbe也称就绪探针，检查容器提供的服务是否能正常访问就提供的服务就绪与否

* Best Practice
1. 存活和就绪的结果处理程序是相互独立的处理程序
2. 不要把健康检查探针的逻辑和你的程序解耦
3. 不要在“存活”探针里实现任何逻辑
4. 在“就绪”检查里实现逻辑，以便检查应用程序的准备情况的详情


* [client-go & controller](https://mp.weixin.qq.com/s/Hz2UqcrOGwa0w_ag_Ww2rA)
* [k8s网络动态](https://mp.weixin.qq.com/s/G4OvFTp5SUvtF8uuSqIcrg)

* [k8s service](https://mp.weixin.qq.com/s/z2kcBK-ixMKpwTo94dC9Xw)
* [k8s-API-Server三部曲](https://mp.weixin.qq.com/s/1doLw7Ko5I4652cssalGCg)