# Kubernetes beginners lab cluster part 1
## without deployment
This environment has been verified in ```minikube```

After check out
```sh
$ kubectl create -f .
```

```sh
$ kubectl get all
NAME                 READY   STATUS    RESTARTS   AGE
pod/postgres-pod     1/1     Running   0          4m15s
pod/redis-pod        1/1     Running   0          4m15s
pod/result-app-pod   1/1     Running   0          4m15s
pod/voting-app-pod   1/1     Running   0          4m15s
pod/worker-app-pod   1/1     Running   0          4m15s

NAME                     TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)        AGE
service/db               ClusterIP      10.110.175.161   <none>        5432/TCP       4m15s
service/kubernetes       ClusterIP      10.96.0.1        <none>        443/TCP        5d12h
service/redis            ClusterIP      10.103.159.88    <none>        6379/TCP       4m15s
service/result-service   LoadBalancer   10.102.116.34    <pending>     80:30029/TCP   4m15s
service/voting-service   LoadBalancer   10.104.183.7     <pending>     80:32688/TCP   4m15s

```


```sh
$ minikube service result-service
|-----------|----------------|-------------|--------------------------|
| NAMESPACE |      NAME      | TARGET PORT |           URL            |
|-----------|----------------|-------------|--------------------------|
| default   | result-service |          80 | http://192.168.1.5:30029 |
|-----------|----------------|-------------|--------------------------|
* Opening service default/result-service in default browser...


$ minikube service voting-service
|-----------|----------------|-------------|--------------------------|
| NAMESPACE |      NAME      | TARGET PORT |           URL            |
|-----------|----------------|-------------|--------------------------|
| default   | voting-service |          80 | http://192.168.1.5:32688 |
|-----------|----------------|-------------|--------------------------|
* Opening service default/voting-service in default browser...

```

But the results not updated when i tryout in browser
