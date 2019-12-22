kubectl create serviceaccount --namespace kube-system tiller
kubectl create clusterrolebinding tiller-cluster-rule --clusterrole=cluster-admin --serviceaccount=kube-system:tiller
helm init --service-account tiller

kubectl get deployments -n kube-system

kubectl apply -f lightsout.yaml


kubectl apply -f studjob.yaml

kubectl create -f ingress.yaml


helm install --name nginx-ingress stable/nginx-ingress

kubectl get service nginx-ingress-controller

