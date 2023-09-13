# rules  
https://awesome-prometheus-alerts.grep.to  

https://www.prometheus.wang/di-wu-zhang-jing-bao/chang-yong-cha-xun-alert-rules  

https://github.com/coreos/kube-prometheus/blob/master/manifests/prometheus-rules.yaml  

https://ranchermanager.docs.rancher.com/zh/integrations-in-rancher/monitoring-and-alerting/promql-expressions  

# dashboards  
https://grafana.com/orgs/wanghy8166/dashboards  

https://github.com/percona/grafana-dashboards/tree/master/dashboards  

https://github.com/grafana/kubernetes-app  

# 云厂商dashboards  
https://github.com/aliyun/aliyun-cms-grafana  

https://github.com/TencentCloud/tencentcloud-monitor-grafana-app  

https://github.com/monitoringartist/grafana-aws-cloudwatch-dashboards  

# 常用exporter  
https://prometheus.io/docs/instrumenting/exporters  

https://github.com/prometheus/prometheus/wiki/Default-port-allocations  

# 自定义exporter  
- 自己写 exporter 暴露指标  
- 自己写脚本发给 pushgateway 暴露指标  
- 通过 https://github.com/prometheus/client_python 写脚本暴露指标  
- 通过 https://github.com/prometheus/client_python 写脚本发给 pushgateway 暴露指标  

- 自己写脚本可以参考以下工具列表  
https://prometheus.io/docs/instrumenting/clientlibs/  

- 此外，也有第三方写好的exporter，直接加脚本套用即可  
https://github.com/gree-gorey/bash-exporter    探测:脚本执行输出  
https://github.com/adhocteam/script_exporter   探测:脚本执行耗时、脚本执行是否成功  
https://github.com/ncabatoff/script-exporter   探测:脚本执行输出、脚本执行耗时、脚本是否在执行中、脚本执行次数  
https://github.com/ricoberger/script_exporter  探测:脚本执行输出、脚本执行耗时、脚本执行是否成功  

# 在业务中集成自定义Metrics,不需要exporter  
https://cloud.tencent.com/document/product/1416/56030  
http://ylzheng.com/2018/01/24/use-prometheus-monitor-your-spring-boot-application/  

# 远端存储方案  
https://prometheus.io/docs/prometheus/latest/storage  

https://prometheus.io/docs/operating/integrations/#remote-endpoints-and-storage  

# mtail日志分析  
实时或近实时监视日志，以用于性能测量和告警，没有ELK的时候就用它吧。  
https://github.com/google/mtail  
1. 在日志更新较快的时候，可以修改scrape_interval:5s让prometheus尽快抓取。
2. 由于抓取始终有间隔，在高并发场景，可以记录"汇总执行时间"、"汇总执行次数"，再换算得出所要的指标。  
具体可参考  
https://github.com/google/mtail/blob/master/docs/Programming-Guide.md#storing-intermediate-state  
https://github.com/google/mtail/blob/master/docs/Programming-Guide.md#computing-moving-averages  
