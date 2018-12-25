Example chart for helm
```bash
Source : https://github.com/erwindeg/k8s-helm 
Youtube tutorial : https://youtu.be/TXZBuBQpm-Q?t=508

Check which Kubernetes context a you connected to (GCP, Minikube, AWS, docker-for-desktop) kubectl get current-context

╭─anidhula@WKMIN2685885 ~/learn/helm/k8s-helm ‹master› 23/Dec/18|15:13:29 
╰─$ kubectl config current-context 


docker-for-desktop

>Check the existing namespaces kubectl get namespaces 


╭─anidhula@WKMIN2685885 ~/learn/helm/k8s-helm ‹master› 23/Dec/18|15:16:52 
╰─$ kubectl get namespaces 


NAME STATUS AGE default Active 15d 
docker Active 15d 
kube-public Active 15d 
kube-system Active 15d 
kubeapps Active 6d

╰─$ pwd /Users/anidhula/learn/helm/k8s-helm

╭─anidhula@WKMIN2685885 ~/learn/helm/k8s-helm ‹master› 23/Dec/18|15:20:50 
╰─$ ls helm_chart_guestbook Chart.yaml templates values.yaml

helm install --name helm-gb-chart --namespace helm-go ./helm_chart_guestbook 

╭─anidhula@WKMIN2685885 ~/learn/helm/k8s-helm ‹master› 23/Dec/18|15:31:05 
╰─$ helm install --name helm-gb-chart --namespace helm-go ./helm_chart_guestbook 
Error: incompatible versions client[v2.12.1] server[v2.11.0]


╭─anidhula@WKMIN2685885 ~/learn/helm/k8s-helm  ‹master›  25/Dec/18|19:41:19
╰─$ kubectl -n helm-go get pods


NAME                            READY   STATUS    RESTARTS   AGE
frontend-6695dc668-nlvrr        1/1     Running   0          4m
frontend-6695dc668-w8r5v        1/1     Running   0          4m
frontend-6695dc668-xpb84        1/1     Running   0          4m
redis-master-6c46f6cfb8-9zkzp   1/1     Running   0          4m
redis-slave-584c66c5b5-k7g7s    1/1     Running   0          4m
redis-slave-584c66c5b5-kz84r    1/1     Running   0          4m


$ kubectl -n helm-go get svc
NAME           TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)        AGE
frontend       NodePort    10.97.148.53    <none>        80:32080/TCP   9m
redis-master   ClusterIP   10.107.167.98   <none>        6379/TCP       9m
redis-slave    ClusterIP   10.106.249.22   <none>        6379/TCP       9m
╭─anidhula@WKMIN2685885 ~/learn/helm/k8s-helm  ‹master›  25/Dec/18|19:50:25
  
  
```
