# rabbitmq-cluster-k8s-operator

### 1. Install a specific version for CSI driver

```console
helm repo add csi-driver-smb https://raw.githubusercontent.com/kubernetes-csi/csi-driver-smb/master/charts
helm install csi-driver-smb csi-driver-smb/csi-driver-smb --namespace kube-system --version v1.17.0
```

### 1. Install the RabbitMQ Cluster Kubernetes Operator

```console
kubectl apply -f cluster-operator.yml
```

### 2. Create smb storage class

```console
kubectl apply -f smb.yml
```

### 3. Add SMB credentials to K8s secret

```console
kubectl apply -f secrets.yml
```

### 4. Create persistent volume

```console
kubectl apply -f rabbitmq-pv.yml
```

### 5. Deploy the RabbitMQ Cluster

```console
kubectl apply -f rabbitmq-cluster.yml
```
