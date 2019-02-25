## 容器日志系统方案

### 容器应用的日志输出方式
1. 输出到stdout/stderr
2. 输出到容器里面log文件
3. 应用直接输出到后端日志系统

### 具体日志收集和管理方案
1. Node上以DaemonSet方式部署log-agent
  * 要求容器应用日志输出到stdout/stderr
  * log-agent(如Fluend)将日志文件转发到ES等后端日志系统以供查询
  * 方案架构图
    ![方案1架构图](../images/log_1.png)
2. 以Sidecar方式将容器日志文件转成stdout/stderr，继续以1中log-agent的方案
  * 容器应用日志输出到log文件
  * Sidecar容器将log文件转成stdout/stderr
  * 方案架构图
    ![方案2架构图](../images/log_2.png)
3. 直接以log-agent(如Fluentd)为Sidecar，将日志文件转发到后端日志系统 
  * 容器应用日志输出到log文件
  * Sidecar方式的log-agent直接将日志转发到后端日志系统
  * 方案架构图
    ![方案3架构图](../images/log_3.png)
4. 容器应用直接写日志到后端日志系统
  * 方案架构图
    ![方案4架构图](../images/log_4.png)   
    
### 参考资料
* [容器日志收集与管理](https://time.geekbang.org/column/article/73156)