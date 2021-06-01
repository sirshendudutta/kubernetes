# kubectl apply commands in order :
<n>kubectl apply -f mongo-secret.yaml
<n>kubectl apply -f mongo.yaml
<n>kubectl apply -f mongo-configmap.yaml 
<n>kubectl apply -f mongo-express.yaml

# kubectl get commands :
<n>kubectl get pod
<n>kubectl get pod --watch
<n>kubectl get pod -o wide
<n>kubectl get service
<n>kubectl get secret
<n>kubectl get all | grep mongodb

# kubectl debugging commands :
<n>kubectl describe pod mongodb-deployment-xxxxxx
<n>kubectl describe service mongodb-service
<n>kubectl logs mongo-express-xxxxxx

# give a URL to external service in minikube :
<n>minikube service mongo-express-service
