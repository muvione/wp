# EKS Cluster with Wordpress and MySQL using eksctl and Helm
This repository provides steps to create a Kubernetes cluster on AWS using eksctl and deploy Wordpress and MySQL using Helm.

## Requirements
- AWS account
- eksctl
- Helm
- Kubectl

## Creating the Cluster
Create a cluster configuration file named cluster.yaml and run the following command to create the cluster
`eksctl create cluster -f cluster.yaml`

Get the credentials for the cluster using the following command:
`aws eks update-kubeconfig --name cluster1`

## Deploying Wordpress and MySQL
- Create a PersistentVolumeClaim (PVC) for both Wordpress and MySQL to store data permanently.
- Create services for Wordpress and MySQL. Use an Elastic Load Balancer (ELB) for the Wordpress pods and a ClusterIp service for the MySQL pods.
- Create Wordpress and MySQL deployments using kustomization.yaml file.

## Deploying Wordpress using Helm
- Install Helm.
- Create a Wordpress and MariaDB application using the Bitnami repository.

## Prometheus and Grafana
- Prometheus is used for monitoring kubernetes cluster. It shows overall CPU / Memory / Filesystem usage as well as individual pod, containers, systemd services statistics.
- Grafana is open source visualization and analytics software. It allows you to query, visualize, alert on, and explore your metrics no matter where they are stored.
- You can setup prometheus and Grafana for your kubernetes cluster using Helm charts


# Conclusion
- By following the steps in this repository, you should now have a fully functional Wordpress and MySQL deployment on your EKS cluster using eksctl and Helm.
- For detailed info, checkout my article [Click Here](https://medium.com/@kvs-vishnu23/understanding-amazon-eks-aws-fargate-kubernetes-and-helm-by-deploying-a-wordpress-application-8c8aa79fa3e6)
