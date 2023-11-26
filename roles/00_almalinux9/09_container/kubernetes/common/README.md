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
sed -i s/KUBELET_EXTRA_ARGS=/KUBELET_EXTRA_ARGS=--node-ip=xxx.xxx.xxx.xxx/g /etc/sysconfig/kubelet

kubeadm init --pod-network-cidr=xxx.xxx.xxx.xxx/xx --apiserver-advertise-address=xxx.xxx.xxx.xxx
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
export KUBECONFIG=/etc/kubernetes/admin.conf

kubectl create -f https://raw.githubusercontent.com/projectcalico/calico/v3.26.4/manifests/tigera-operator.yaml
kubectl create -f https://raw.githubusercontent.com/projectcalico/calico/v3.26.4/manifests/custom-resources.yaml
```

If the process comes to a halt
```
find /etc/kubernetes -type f | xargs sed -i s/xxx.xxx.xxx.xxx/[correct IP address]/g
```

Renew certificate
```
kubeadm certs renew all
```

Renew a certificate by specifying an IP address
```
rm /etc/kubernetes/pki/apiserver.* -f
kubeadm init phase certs apiserver --apiserver-cert-extra-sans xxx.xxx.xxx.xxx --apiserver-cert-extra-sans xxx.xxx.xxx.xxx --apiserver-cert-extra-sans localhost
```

Reset
```
kubeadm reset
```

Author Information
------------------

- snkk1210