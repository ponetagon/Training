# Kubernetes Lab README

This README provides an overview of the various Kubernetes YAML configurations used in this lab. Each file serves a specific purpose in deploying and managing applications in a Kubernetes environment.

## Kubernetes Cheat Sheet

https://kubernetes.io/pt-br/docs/reference/kubectl/cheatsheet/

## Kubernetes Basic Commands

### 1. Get Resources
Retrieve information about various resources in the cluster.

- Get all Pods:
  ```bash
    kubectl get pods  # Get all Pods in the current namespace

    kubectl expose pod <pod-name> --type=<service-type> --port=<port>  # Expose a Pod as a service

    kubectl logs <pod-name>  # Retrieve logs from a Pod

    kubectl exec -it <pod-name> -- <command>  # Execute a command in a running Pod

    kubectl create -f <filename>.yaml  # Create a resource from a file or stdin

    kubectl apply -f <filename>.yaml  # Apply a configuration change to a resource

    kubectl run <pod-name> --image=<image-name>  # Run a particular image as a Pod

    kubectl edit <resource-type>/<resource-name>  # Edit a resource in place (opens in an editor)

    kubectl delete <resource-type> <resource-name>  # Delete a resource

    kubectl scale deployment <deployment-name> --replicas=<number>  # Scale a Deployment or ReplicaSet

    kubectl top pods  # Display resource usage (CPU and memory)

    kubectl describe pod <pod-name>  # Describe a resource to get detailed information

## Lab Contents

1. **pod.yaml**  
   Defines a basic Pod specification for deploying single or multiple containers.

2. **deployment.yaml**  
   Configures a Deployment to manage the lifecycle of a set of replicas of a Pod.

3. **deployment-resource.yaml**  
   Demonstrates setting resource requests and limits for a Deployment to manage CPU and memory usage.

4. **deployment-health-http.yaml**  
   Configures HTTP health checks for a Deployment to ensure that the application is responsive.

5. **deployment-health-tcp.yaml**  
   Configures TCP health checks for a Deployment to ensure that the application is reachable on a specific port.

6. **deployment-emptydir.yaml**  
   Demonstrates the use of an EmptyDir volume for temporary storage that is shared between containers in a Pod.

7. **deployment-hostpath.yaml**  
   Shows how to use HostPath volumes to mount a directory from the host node’s filesystem into a Pod.

8. **static-pv.yaml**  
   Defines a Static Persistent Volume (PV) that can be used to provide storage to Pods.

9. **dynamic-pv.yaml**  
   Configures a Dynamic Persistent Volume (PV) that allows for automated provisioning of storage resources.

10. **mysql-secret.yaml**  
    Creates a Secret to store sensitive data (e.g., MySQL root password) securely.

11. **mysql-configmap.yaml**  
    Configures a ConfigMap for storing non-sensitive configuration data for MySQL.

12. **mysql-pvc.yaml**  
    Defines a Persistent Volume Claim (PVC) to request storage for the MySQL deployment.

13. **mysql-deployment.yaml**  
    Configures the Deployment for MySQL, specifying the container image and environment variables.

14. **mysql-service.yaml**  
    Sets up a Service to expose the MySQL Deployment, allowing other Pods to communicate with it.

15. **mysql-client.yaml**  
    Creates a Pod that acts as a MySQL client to connect to the MySQL database defined in files 10-14.

16. **blue-deployment.yaml**  
    Configures the blue version of a blue-green deployment strategy.

17. **green-deployment.yaml**  
    Configures the green version of a blue-green deployment strategy.

18. **blue-green-service.yaml**  
    Defines a Service to route traffic to the appropriate version (blue or green) based on deployment strategy.

## Usage

- Ensure you have access to a Kubernetes cluster and `kubectl` installed.
- Apply the configurations in the order listed above using the following command:
  ```bash
  kubectl apply -f <filename.yaml>
