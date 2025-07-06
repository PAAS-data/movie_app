# k8s-deployment-project

This project contains the necessary Kubernetes configurations for deploying a frontend application, a backend application, and a MongoDB database. Below are the details and steps to deploy the applications.

## Project Structure

- **backend-deployment.yaml**: Defines the deployment configuration for the backend application, including container image, replicas, and volume mounts.
- **backend-service.yaml**: Defines the service configuration for the backend application to allow communication with the frontend and other services.
- **frontend-deployment.yaml**: Defines the deployment configuration for the frontend application, specifying the container image, replicas, and necessary environment variables.
- **frontend-service.yaml**: Defines the service configuration for the frontend application to expose it to external clients.
- **mongo.yaml**: Defines the StatefulSet and PersistentVolumeClaim for the MongoDB database, specifying storage requirements and the container image.
- **secret.yaml**: Defines a Kubernetes Secret to securely store sensitive information, such as database connection strings.
- **configmap.yaml**: Defines a ConfigMap to store non-sensitive configuration data, such as environment variables for the applications.

## Steps to Deploy

1. **Create the YAML files**: Use the provided structure to create each YAML file with the appropriate configurations.

2. **Deploy MongoDB**:
   - Run `kubectl apply -f mongo.yaml` to create the MongoDB StatefulSet and PersistentVolumeClaim.

3. **Deploy the Backend**:
   - Run `kubectl apply -f backend-deployment.yaml` to create the backend deployment.
   - Run `kubectl apply -f backend-service.yaml` to expose the backend service.

4. **Deploy the Frontend**:
   - Run `kubectl apply -f frontend-deployment.yaml` to create the frontend deployment.
   - Run `kubectl apply -f frontend-service.yaml` to expose the frontend service.

5. **Create Secrets and ConfigMaps**:
   - Run `kubectl apply -f secret.yaml` to create the secret.
   - Run `kubectl apply -f configmap.yaml` to create the config map.

6. **Verify Deployments**: Use `kubectl get pods` and `kubectl get services` to check the status of your deployments and services.

7. **Access the Applications**: Depending on your service type (ClusterIP, NodePort, LoadBalancer), access the frontend application using the appropriate method.