# gke-google-cloud-kubernetes
 Postgres (Stateful), Keycloak and sample application deployed in Google Cloud Kubernetes.
 
 ## Steps
 
 1) Create Cluster in Google Cloud Kubernates.
 2) Create Postgres Stateful deployment. Use postgres-deployment-service.yaml Deploy it via the Cloud Shell: kubectl apply -f {file}.yaml
 3) Deploy Keycloak as a single container: kubectl apply -f keycloak-deployment-service.yaml
 5) Deploy your sample application and connect it via ENVs to the Postgres DB and Keycloak.
 6) Deploy ingress-more-backends.yaml to expose keycloak and the sample application via one public IP. (services are created as NodePort / Postgres as LoadBalancer has own IP)
 7) Use the features of GKE and scale your Apps. 

## Useful Commands
- kubectl get all -> list all objects in kubernetes
- kubectl apply -f {file}.yaml -> deploy yaml file
- kubectl logs {pod-name} -> log file of container

## Notes
- pods -> smallest unit in kubernetes
- deployment -> defines how much replicas are running in your cluster. ENVs, Ports, Rolling Updates etc. are defined there
- services -> LoadBalancer, Ingress or NodePort

## Useful links
- https://www.bmc.com/blogs/kubernetes-postgresql/
- https://www.keycloak.org/getting-started/getting-started-kube
- https://cloud.google.com/kubernetes-engine/docs/how-to/load-balance-ingress?hl=de#multiple_backend_services
- https://medium.com/google-cloud/kubernetes-nodeport-vs-loadbalancer-vs-ingress-when-should-i-use-what-922f010849e0