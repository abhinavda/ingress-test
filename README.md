# ingress-test

eval $(minikube -p minikube docker-env)

cd ~/projects/git/new_projects/ingress-test

docker build -t webapp:1.0 .

docker run -d -p 80:8000 --name web webapp:1.0

> minikube ip

Verify the image is present in the minikube Docker daemon:
minikube ssh
docker image ls
