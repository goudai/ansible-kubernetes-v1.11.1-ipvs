# ansible-kubernetes-v1.11.1-ipvs

```shell
docker pull mirrorgooglecontainers/kube-proxy-amd64:v1.12.3
docker pull mirrorgooglecontainers/kube-scheduler-amd64:v1.12.3
docker pull mirrorgooglecontainers/kube-controller-manager-amd64:v1.12.3
docker pull mirrorgooglecontainers/kube-apiserver-amd64:v1.13.3
docker pull mirrorgooglecontainers/etcd-amd64:3.2.24-1
docker pull coredns/coredns:1.2.6
docker pull mirrorgooglecontainers/kube-proxy-amd64:v1.12.3
docker pull mirrorgooglecontainers/metrics-server-amd64:v0.3.1
docker pull mirrorgooglecontainers/pause-amd64:3.1

systemctl stop kubelet && docker rm $(docker ps -qa) -f && rm -rf /var/lib/etcd/ && rm -rf /etc/kubernetes/ && rm -rf  /etc/etcd/ && rm -rf /etc/haproxy/
```
docker run -it --name tmp --rm docker.io/freemanliu/kube sleep 100 & 
docker cp tmp:/opt/kubernetes-server-linux-amd64.tar.gz .
tar -zxvf kubernetes-server-linux-amd64.tar.gz  --strip-components=3 -C /usr/local/bin kubernetes/server/bin/kube{let,ctl,-apiserver,-controller-manager,-scheduler,-proxy}
使用指南: https://www.qingmu.io/2018/07/31/Kubernetes-v1-11-1-ansible/
