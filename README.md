# kambly

![status-draft](https://img.shields.io/badge/Status-Draft-orange)

Kops managed K8s cluster on Infomaniak openstack

## Current Status

- [ ] DNS (and probably internet access in general) does not work)
- [ ] [Automated Setup](https://kops.sigs.k8s.io/continuous_integration/) is desired 

## Preparation

- Create opennstack project
- Create application credentials (and download rc file)
- export Env vars in shell

## Initial creation

```bash
kops create cluster --cloud=openstack --name kambly.k8s.local --zones 'dc3-a-04,dc3-a-10,dc3-a-09' --network-cidr 10.123.0.0/16 --image 'Ubuntu 22.04 LTS Jammy Jellyfish' --master-count=1 --node-count=1--node-size a2-ram4-disk20-perf1 --master-size a2-ram4-disk20-perf1 --etcd-storage-type CEPH_1_perf1 --api-loadbalancer-type public  --topology private --ssh-public-key ~/.ssh/id_yubikey  --networking cilium --os-ext-net ext-floating1  --os-octavia=true --yes
```

