# Install EKS

Please follow the prerequisites doc before this.

## Install a EKS cluster with EKSCTL

```
eksctl create cluster --name go-web-app --region us-east-1 
```

## Delete the cluster

```
eksctl delete cluster --name go-web-app --region us-east-1
```
## ingress info
```
kubectl get ing
```
## edit service:
```
kubectl edit svc go-web-app
```
## check node ip details:
```
kubectl get nodes -o wide
```
18.234.132.4:31634
54.236.227.145:31634

## fix connection issue of secuirty-group
```
aws ec2 authorize-security-group-ingress --group-id sg-0054e2f8420ec88ab --protocol tcp --port 31634 --cidr 0.0.0.0/0
```