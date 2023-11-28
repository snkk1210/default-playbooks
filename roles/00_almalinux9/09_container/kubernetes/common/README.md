kubernetes/common
=========

## これは何？

kubernetes を導入する Playbook です。

## Dependencies

none

## 変数

none

## Memo

Commands after provisioning for control plane
```
kubeadm init --pod-network-cidr=xxx.xxx.xxx.xxx/xx --control-plane-endpoint=xxx.xxx.xxx.xxx --apiserver-advertise-address=xxx.xxx.xxx.xxx --service-cidr=xxx.xxx.xxx.xxx/xx

mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config
export KUBECONFIG=/etc/kubernetes/admin.conf
```

Install Calico
```
kubectl create -f https://raw.githubusercontent.com/projectcalico/calico/v3.26.4/manifests/tigera-operator.yaml
wget https://raw.githubusercontent.com/projectcalico/calico/v3.26.4/manifests/custom-resources.yaml
kubectl create -f custom-resources.yaml
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

Reset kube setup
```
kubeadm reset
```

Rewrite IP address directly
```
find /etc/kubernetes -type f | xargs sed -i s/xxx.xxx.xxx.xxx/[correct IP address]/g
```

Author Information
------------------

- snkk1210