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
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
export KUBECONFIG=/etc/kubernetes/admin.conf

kubectl create -f https://raw.githubusercontent.com/projectcalico/calico/v3.26.4/manifests/tigera-operator.yaml
kubectl create -f https://raw.githubusercontent.com/projectcalico/calico/v3.26.4/manifests/custom-resources.yaml
```

Author Information
------------------

- snkk1210