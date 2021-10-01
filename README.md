===============================================================================================
#Using the Repo  for  Running Containerized React Application using the Kubernetes and Docker

-> Generating the dockerconfig  Secret to  connect  docker hub

echo "username:password" |base64

echo "{  "auths": {    "https://index.docker.io/v1/": { "auth": "Encoded Username and Password" } }}" |base64

Place  the Encoded String to Secrets


-> Presently we have Seperate  Manifest  files  for   Service,namespace and Deployments.  Here  in the Application I am using  A  single  deployment file  called  "Secrets.yml"  for the Deployment

============================================================================================================================
-->  A  Docker Image  is  built and placed in the Docker Hub  which has the react  app containerized 
-> Repo has the Dockerfile  Included 


Below are the commands for Docker File 

docker buiild -t venubharadwaj/reactapps:0.2 ./
docker tag reactjscalc:0.2 venubharadwaj/reactapps:0.2
docker push venubharadwaj/reactapps:0.2

Minikube start:
minikube start


Below  are the commands for Kubernetes:

kubectl  apply -f namespace.yml -> Creates a Namespace
kebectl apply -f Secrets.yml ->  Everything comes  here for  running Kubernetes






