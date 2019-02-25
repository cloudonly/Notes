### Kubernetes

#### Pod Probe(探针)
* Liveliness
  
* Readiness

LivelinessProbe也称存活探针，检查容器是否正常运行即存活与否

ReadinessProbe也称就绪探针，检查容器提供的服务是否能正常访问就提供的服务就绪与否

* Best Practice
1. 存活和就绪的结果处理程序是相互独立的处理程序
2. 不要把健康检查探针的逻辑和你的程序解耦
3. 不要在“存活”探针里实现任何逻辑
4. 在“就绪”检查里实现逻辑，以便检查应用程序的准备情况的详情

#### Ingress

* 为了代理不同后端 Service 而设置的负载均衡服务，就是k8s项目的Ingress服务
* 所谓Ingress即是，Service的Service
* 常用的Ingress控制器有nginx/traefik/kong等等
* Ingress对象是k8s项目对“反向代理”一种抽象

```yaml
apiVersion: extensions/v1beta1
kind: Ingress
metadata:
  name: cafe-ingress
spec:
  tls:
  - hosts:
    - cafe.example.com
    secretName: cafe-secret
  rules:
  - host: cafe.example.com
    http:
      paths:
      - path: /tea
        backend:
          serviceName: tea-svc
          servicePort: 80
      - path: /coffee
        backend:
          serviceName: coffee-svc
          servicePort: 80

```

* IngressRule host对应的FQDN, path对应一个个的service
* IngressController根据的IngressRule的变化更新对应的configFile
* IngressController负责负载均衡和转发


#### 参考资料
* [client-go & controller](https://mp.weixin.qq.com/s/Hz2UqcrOGwa0w_ag_Ww2rA)
* [k8s网络动态](https://mp.weixin.qq.com/s/G4OvFTp5SUvtF8uuSqIcrg)

* [k8s service](https://mp.weixin.qq.com/s/z2kcBK-ixMKpwTo94dC9Xw)
* [k8s-API-Server三部曲](https://mp.weixin.qq.com/s/1doLw7Ko5I4652cssalGCg)