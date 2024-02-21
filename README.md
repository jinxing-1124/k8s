請先閱讀 [Kubernetes](https://kubernetes.io/docs/home/)
相關資訊



這個範例是將前後端程式部署到GKE上面的設定檔，

GKE Cluster mode 是 autopilot

GKE 使用的是 VPC-native clusters，因為 VPC-native clusters 有別於地端的 Cluster VPC，它可以與在同一個 VPC 下的服務進行溝通，
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
