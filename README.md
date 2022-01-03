# ingress-test

minikube start --driver=docker --cpus 2 --memory 3000

minikube addons enable ingress

cd ~/projects/git/new_projects/ingress-test

eval $(minikube -p minikube docker-env)

docker build -t webapp:1.0 .

docker run -d -p <localport>:<container port> <container-name> <image>:<tag>

docker run -d -p 8001:8000 --name web webapp:1.0

---
helm template :

helm create webapp

Install helm chart :

helm install web webapp/

export NODE_PORT=$(kubectl get --namespace default -o jsonpath="{.spec.ports[0].nodePort}" services web-webapp)

export NODE_IP=$(kubectl get nodes --namespace default -o jsonpath="{.items[0].status.addresses[0].address}")

echo http://$NODE_IP:$NODE_PORT

helm list

> minikube ip

minikube service web-webapp --url 

---
Verify the image is present in the minikube Docker daemon:

minikube ssh

docker image ls


---
#Cleanup
---------

helm :
---------
 helm delete web

 docker :
 ---------
 docker stop web

 docker rm web
