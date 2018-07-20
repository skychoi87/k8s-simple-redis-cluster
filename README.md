# redis-cluster
statefulset & redis persistence Vol using k8s hostpath

## edit 'redis-cluster.yaml' first
(kubectl create ns redis)

kubectl apply -f redis-cluster.yaml

## manage redis-cluster
kubectl run ubuntu-test -n redis --rm=false -ti --image ubuntu /bin/bash

apt-get update

apt-get install -y ruby vim wget redis-tools

wget http://download.redis.io/redis-stable/src/redis-trib.rb

chmod +x redis-trib.rb

gem install redis


./redis-trib.rb


./redis-trib.rb create --replicas 0 192.168.0.111:7000 192.168.0.112:7000 {redis-pod-ip}:7000

redis-cli -c -h {service-ip} -p 7000

\>set key test

\>get key

\>del key

