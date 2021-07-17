# gke-google-cloud-kubernates
 Postgres, Keycloak and sample application deployed in Google Cloud Kubernates.
 
 ## Steps
 
 1) Create Cluster in Google Cloud Kubernates.
 2) Create Postgres Stateful deployment. Use postgres.yaml and postgres-service.yaml. Deploy it via the Cloud Shell: kubectl apply -f {file}.yaml
 3) Deploy Keycloak as a single container: kubectl apply -f keycloak.yaml
 5) Deploy your sample application and connect it via ENVs to the Postgres DB and Keycloak.
 6) Add Ingress Load-Balancer to expose the applications. (Expose the right Ports and route them to the correct internal cluster ports)
 7) Use the features of GKE and scale your Apps. 

## Useful links
- https://www.bmc.com/blogs/kubernetes-postgresql/
- https://www.keycloak.org/getting-started/getting-started-kube
