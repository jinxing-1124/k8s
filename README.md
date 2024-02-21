若還不了解[Kubernetes](https://kubernetes.io/docs/home/)
可以先點此連結


情境描述

這個範例是將前後端程式部署到GKE上面的設定檔，

GKE Cluster mode 是 autopilot

GKE 使用的是 VPC-native clusters，因為 VPC-native clusters 有別於地端的 Cluster VPC，它可以透過 VPC Peering，與其他 GCP 服務的 VPC network 進行溝通，
詳細資訊可至[官網](https://cloud.google.com/kubernetes-engine/docs/concepts/alias-ips?hl=zh-cn)查詢




## 部署流程
- 先部署前後端的 deployment.yaml
```
kubectl apply -f deployment.yaml
```

- 部署service.yaml
```
kubectl apply -f service.yaml
```

- 最後部署ingress.yaml
```
kubectl apply -f demo-ingress.yaml
```
