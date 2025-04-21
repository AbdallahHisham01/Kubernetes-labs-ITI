## Installation Source

The NGINX Ingress Controller was installed using the official manifests from:

https://docs.nginx.com/nginx-ingress-controller/installation/installing-nic/installation-with-manifests/

## Lab 

Ingress and services:

Create namespace called iti-45
Create 2 deployments in world namespace:
africa with 2 replicas and image “husseingalal/africa:latest”
europe with 2 replicas and image “husseingalal/europe:latest”

Using kubectl expose create ClusterIP Services for both Deployments for port 8888 and target port 80 . The Services should have the same name as the Deployments.

Create a new Ingress resource called world for domain name world.universe.mine . The domain points to the K8s Node IP via /etc/hosts . The Ingress resource should have two routes pointing to the existing Services:

http://world.universe.mine/europe/

and

http://world.universe.mine/africa/
