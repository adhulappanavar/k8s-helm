Example chart for helm

Source : https://github.com/erwindeg/k8s-helm 
Youtube tutorial : https://www.youtube.com/watch?v=TXZBuBQpm-Q

Check which Kubernetes context a you connected to (GCP, Minikube, AWS, docker-for-desktop) kubectl get current-context

╭─anidhula@WKMIN2685885 ~/learn/helm/k8s-helm ‹master› 23/Dec/18|15:13:29 ╰─$ kubectl config current-context 1 ↵ docker-for-desktop

Check the existing namespaces kubectl get namespaces ╭─anidhula@WKMIN2685885 ~/learn/helm/k8s-helm ‹master› 23/Dec/18|15:16:52 ╰─$ kubectl get namespaces NAME STATUS AGE default Active 15d docker Active 15d kube-public Active 15d kube-system Active 15d kubeapps Active 6d

╰─$ pwd /Users/anidhula/learn/helm/k8s-helm

╭─anidhula@WKMIN2685885 ~/learn/helm/k8s-helm ‹master› 23/Dec/18|15:20:50 ╰─$ ls helm_chart_guestbook Chart.yaml templates values.yaml

helm install --name helm-gb-chart --namespace helm-go ./helm_chart_guestbook ╭─anidhula@WKMIN2685885 ~/learn/helm/k8s-helm ‹master› 23/Dec/18|15:31:05 ╰─$ helm install --name helm-gb-chart --namespace helm-go ./helm_chart_guestbook Error: incompatible versions client[v2.12.1] server[v2.11.0]

