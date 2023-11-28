kubernetes/common
=========

## What is this ?

This is a Playbook to introduce kubernetes.

## Dependencies

none

## variable

none

## Memo
### Initialization ( Commands after provisioning )
 Initialization for control plane
```
kubeadm init --pod-network-cidr=xxx.xxx.xxx.xxx/xx --control-plane-endpoint=xxx.xxx.xxx.xxx --apiserver-advertise-address=xxx.xxx.xxx.xxx --service-cidr=xxx.xxx.xxx.xxx/xx

# For regular User
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config

# For root User
export KUBECONFIG=/etc/kubernetes/admin.conf
```

IP address settings for control plane and worker plane
```
sed -i s/KUBELET_EXTRA_ARGS=/KUBELET_EXTRA_ARGS=--node-ip=xxx.xxx.xxx.xxx/g /etc/sysconfig/kubelet

systemctl daemon-reload
systemctl restart kubelet
```

Install Calico for control plane
```
kubectl create -f https://raw.githubusercontent.com/projectcalico/calico/v3.26.4/manifests/tigera-operator.yaml
wget https://raw.githubusercontent.com/projectcalico/calico/v3.26.4/manifests/custom-resources.yaml
sed -i 's/cidr: 192.168.0.0\/16/cidr: xxx.xxx.xxx.xxx\/xx/g' ./custom-resources.yaml
kubectl create -f custom-resources.yaml
```
### Other
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