情境描述

這個範例是將前後端程式部署到GKE上面的設定檔，

GKE Cluster mode 是 autopilot

GKE 使用的是 VPC-native clusters，詳細資訊可至[官網](https://cloud.google.com/kubernetes-engine/docs/concepts/alias-ips?hl=zh-cn)查詢



## deployment介紹
Deployments 顧名思義掌控了部署 Kubernetes 服務的一切。它主要掌管了 Replica Set 的個數，而 Replica Set 的組成就是一個以上的 Pod。

1. Deployments 的設定檔，可以設定 replica 的數量運作
2. Deployments 會檢查 pod 的狀態
3. Deployments 下可執行滾動更新或者 rollback


## service介紹
Kubernetes Service 是個抽象化的概念，主要定義了邏輯上的一群 Pod 以及如何存取他們的規則，以下是它的特性
1. 每個 Service 介接一個以上的 pod
2. 每個 Service 有個獨立且固定的 IP 地址 – Cluster IP
3. 客戶端訪問 Service 時，會經由 proxy 來達到負載平衡



## ingress介紹
- 在GKE 中，Ingress 物件定義用於將HTTP(S) 路由到cluster中運行應用的規則。一個 Ingress 物件與一個或多個Service 物件相關聯。



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
