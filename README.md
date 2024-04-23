# BillingApp# How to make this orquestration
1. Check minikube docker  en 
```sh
minikube docker-env
```
2. To point your shell to minikube's docker-daemon
```sh
 eval $(minikube -p minikube docker-env)
```
3. Build docker bakend images 
```sh
cd backend/
docker build -t billingapp-back:0.0.4 --no-cache --build-arg JAR_FILE=./*jar .
```
4. Build docker FrontEnd images 
```sh
cd ../frontend/
docker build -t billingapp-front:0.0.4 --no-cache .
cd ..
```
5. apply the yaml file
```sh
./run.sh
```	