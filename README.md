Lab2 Instructions

Lab Env :
OS: Ubuntu Server 18.04.1.LTS
Kernel: 4.15.0.39-generic
Docker: 18.06.1-ce With Go version 1.10.3
Memory: 24 GB
SSD: 100GB

ibmdemo: passw0rd
db2inst1 : db2inst1

ICP: Login
Dashboard 

Configure Client


Copy Commands:
kubectl config set-cluster cluster.local --server=https://192.168.142.140:8001 --insecure-skip-tls-verify=true
kubectl config set-context cluster.local-context --cluster=cluster.local
kubectl config set-credentials admin --token=eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdF9oYXNoIjoiMjk0eG85bTVkZG15NnZ2cTVyajAiLCJyZWFsbU5hbWUiOiJjdXN0b21SZWFsbSIsInVuaXF1ZVNlY3VyaXR5TmFtZSI6ImFkbWluIiwiaXNzIjoiaHR0cHM6Ly9teWNsdXN0ZXIuaWNwOjk0NDMvb2lkYy9lbmRwb2ludC9PUCIsImF1ZCI6ImQ4Njk5NDhiM2YyMjA0OWMyMzMxOWFhMjc1MmZjZjVjIiwiZXhwIjoxNTUzODIwMzYyLCJpYXQiOjE1NTM3OTE1NjIsInN1YiI6ImFkbWluIiwidGVhbVJvbGVNYXBwaW5ncyI6W119.vr1G6v0HiVEh6Ep3lItGumO6nztllCqS0QCIrNxt1JzH_1ZRlukZQHf13IVhctWAKnqAS-bNuBDK1vZwHYCxAdDLoli4eXQPdiZ2qMfT2rwwnMu4Ft76hVJ3FAwh0ZUFWg1o9dvi0UZcGdx1IVj4aBZqTwyE7LAPXE5TKietFG_z_etRdTzFdyoCUSeVLcEQVUGX_D9X9SJHQMQh8yPXCaay7Ru9Pp0C1uOCRxvo3IYMAdW64h79nxQE3d22UoQkbg-5qgOimKeKiKt991R2nK6rto2DxM572sDwJRWOwsGeGWT7W-euOXjKtIcZH_gc_q1AgFycbfkB8l8-OzLm1Q
kubectl config set-context cluster.local-context --user=admin --namespace=cert-manager
kubectl config use-context cluster.local-context

Go to Terminal and paste the above commands

You will see the following:

ibmdemo@ubuntuvm1:~$ pwd
/home/ibmdemo
ibmdemo@ubuntuvm1:~$ kubectl config set-cluster cluster.local --server=https://192.168.142.140:8001 --insecure-skip-tls-verify=true
Cluster "cluster.local" set.
ibmdemo@ubuntuvm1:~$ kubectl config set-context cluster.local-context --cluster=cluster.local
Context "cluster.local-context" modified.
ibmdemo@ubuntuvm1:~$ kubectl config set-credentials admin --token=eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdF9oYXNoIjoiMjk0eG85bTVkZG15NnZ2cTVyajAiLCJyZWFsbU5hbWUiOiJjdXN0b21SZWFsbSIsInVuaXF1ZVNlY3VyaXR5TmFtZSI6ImFkbWluIiwiaXNzIjoiaHR0cHM6Ly9teWNsdXN0ZXIuaWNwOjk0NDMvb2lkYy9lbmRwb2ludC9PUCIsImF1ZCI6ImQ4Njk5NDhiM2YyMjA0OWMyMzMxOWFhMjc1MmZjZjVjIiwiZXhwIjoxNTUzODIwMzYyLCJpYXQiOjE1NTM3OTE1NjIsInN1YiI6ImFkbWluIiwidGVhbVJvbGVNYXBwaW5ncyI6W119.vr1G6v0HiVEh6Ep3lItGumO6nztllCqS0QCIrNxt1JzH_1ZRlukZQHf13IVhctWAKnqAS-bNuBDK1vZwHYCxAdDLoli4eXQPdiZ2qMfT2rwwnMu4Ft76hVJ3FAwh0ZUFWg1o9dvi0UZcGdx1IVj4aBZqTwyE7LAPXE5TKietFG_z_etRdTzFdyoCUSeVLcEQVUGX_D9X9SJHQMQh8yPXCaay7Ru9Pp0C1uOCRxvo3IYMAdW64h79nxQE3d22UoQkbg-5qgOimKeKiKt991R2nK6rto2DxM572sDwJRWOwsGeGWT7W-euOXjKtIcZH_gc_q1AgFycbfkB8l8-OzLm1Q
User "admin" set.
ibmdemo@ubuntuvm1:~$ kubectl config set-context cluster.local-context --user=admin --namespace=cert-manager
Context "cluster.local-context" modified.
ibmdemo@ubuntuvm1:~$ kubectl config use-context cluster.local-context
Switched to context "cluster.local-context".
ibmdemo@ubuntuvm1:~$ 


Now type:  kubectl -n kube-system get pods

kubectl get secrets

IBM Cloud CLI Command
cloudctl

ibmdemo@ubuntuvm1:~$ cloudctl login -a https://192.168.142.140:8443 --skip-ssl-validation

kubernetes commands

kubectl version

kubectl get componentstatuses


============
Lab3

cd lab3

kubectl apply -f kube01.yaml

kubectl get pods | grep ghost

kubectl get pods -o wide | grep ghost

kubectl port-forward ghost 2368:2368

Keep it running and open a browser and type
http://localhost:2368

kubectl delete pod ghost


================

kubectl apply -f kube02.yaml






