Steps:
1. Create the python files for model training and execution. 
2. Create the docker files for model training and execution. 
3. Push the docker files onto dockerhub using the commands given in the PDF. 

docker build -t dockerfile .
docker login -u ns4451docker
docker tag dockerfile:latest ns4451docker/cmlhw5
docker push ns4451docker/cmlhw5

4. Create the 3 yaml files for PVC, training, and load balancer service and deployment. 
5. Apply the yaml files using the apply commands given in the PDF. 

kubectl apply -f mypvc.yaml
kubectl apply -f training.yaml
kubectl apply -f deploymentservice.yaml

6. Ping the test image via the flask server on the port specified in the yaml and python file. 

curl --request POST -F "image=@testimage.jpg" http://localhost:5000/inference