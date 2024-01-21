## Deploy-to-Kubernetes

To deploy your API to Kubernetes, follow these steps:

Set up a Kubernetes cluster: Depending on your requirements, you can set up a local Kubernetes cluster using Minikube or a cloud-based cluster using services like Azure Kubernetes Service (AKS) or Amazon Elastic Kubernetes Service (EKS). I’ll be using Minikube for this example, you can follow this doc: https://minikube.sigs.k8s.io/docs/start/
Please note that installing and starting your local minikube Kubernetes environment or the first time may take some time and a few machine restarts. I’ve also had several issues starting minikube in windows and using the following command fixed the problem:

    minikube start --hyperv-use-external-switch --driver=docker --docker-env=local

#### This is a breakdown of the previous command:
minikube start: This command starts Minikube and sets up a local Kubernetes cluster.
    --hyperv-use-external-switch: This flag is specific to the Hyper-V driver. It instructs Minikube to use an external virtual switch for networking instead of creating an internal virtual switch. This can be helpful if you want to connect your cluster to the network or access it from other machines.
    --driver=docker: This flag specifies the driver to be used by Minikube. In this case, it sets the driver to Docker, indicating that Minikube should use the Docker driver for managing the Kubernetes cluster.
    --docker-env=local: This flag is used to configure Minikube to use the local Docker environment. By setting it to local, Minikube will utilize the Docker daemon on your local machine rather than spinning up a separate virtual machine for Docker.

When you execute this command, Minikube will start and create a single-node Kubernetes cluster using the Docker driver and the local Docker environment.

Now we should be able to open the Kubernetes dashboard:
```
minikube dashboard
```
![image](https://github.com/biplobpustcse/Deploy-to-Kubernetes/assets/59637279/8ed725f0-6eba-4300-87d5-678df340d560)

Lets now deploy our weather API to Kubernetes :)
