kubernetes/common
=========

## これは何？

kubernetes を導入する Playbook です。

## Dependencies

- common

## 変数

none

## Memo

Commands after provisioning for control plane
```
kubeadm init --pod-network-cidr=xxx.xxx.xxx.xxx/xx
export KUBECONFIG=/etc/kubernetes/admin.conf
kubectl create -f https://raw.githubusercontent.com/projectcalico/calico/v3.25.1/manifests/tigera-operator.yaml
kubectl create -f https://raw.githubusercontent.com/projectcalico/calico/v3.25.1/manifests/custom-resources.yaml
```

Author Information
------------------

- snkk1210