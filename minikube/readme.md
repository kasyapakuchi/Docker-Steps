Minikube steps
-----------------

1. install kompose <code>curl -L https://github.com/kubernetes/kompose/releases/download/v1.26.0/kompose-windows-amd64.exe -o kompose.exe</code>

2. Create deployment yamls from the existing <code>docker-compose.yaml</code>. Sample <code>docker-compose.yml</code> and created <code>deployment.yaml</code> files are attached in the repo. - Run the command <code>kompose convert</code>

3. Change image pull policy in the deployment.yamls as needed. In our case we made it Never as we want to use local image always and do not pull from Docker registry.

<code>imagePullPolicy: Never</code>

4. Install Minikube. Refer - https://minikube.sigs.k8s.io/docs/start/
5. start the minikube with docker driver, instead of default driver. <code>minikube start --driver=docker</code>
6. Set up the minikube for docker env. <code>minikube docker-env</code>
7. Setup minikube registry
<code>minikube addons enable registry</code>

8. Build images again to create images in minikube registry

<code>eval $(minikube docker-env)</code><br \>
<code>docker build --tag=vaccine-vendor:latest .</code><br \><br \>

<code>eval $(minikube docker-env)</code><br \>
<code>docker build --tag=patient-service-2:latest .</code><br \><br \>

<code>eval $(minikube docker-env)</code><br \>
<code>docker build --tag=hospital-service:latest .</code><br \>


9. kubectl apply to deploy containers in the kubernates cluster

<code>kubectl apply -f patient-service-service.yaml,patient-service-deployment.yaml,vaccine-vendor-service.yaml,vaccine-vendor-deployment.yaml,hospital-service-service.yaml,hospital-service-deployment.yaml</code>

10. verify services are up

<code>kubectl get pods</code>
<code>kubectl get deployments</code>




