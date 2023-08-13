** 1. Choice of Kubernetes Objects ** 

For deploying a frontend and backend Node.js app with MongoDB, you can use the following Kubernetes objects:

    Deployments: For both frontend and backend, to manage the desired number of replicas, rolling updates, and scaling.
    Services: To expose your frontend and backend deployments to internal and external traffic.
    StatefulSets: For MongoDB, as a stateful application that requires persistent storage.

** 2. Use of StatefulSets **

MongoDB is a database that requires data persistence and consistent network identities. Therefore, a StatefulSet is a suitable choice for deploying MongoDB:

    MongoDB StatefulSet: A StatefulSet for MongoDB ensures ordered pod creation, stable network identities (important for database replication), and persistent storage for data. Each pod in the StatefulSet maintains its own identity and persistent volume.

** 3. Method to Expose Pods to Internet Traffic **

For exposing your frontend and backend to internet traffic, you can use LoadBalancer type services:

    Frontend Service (LoadBalancer): Exposes the frontend to the internet, distributing traffic across the replicas. Users access your app via a public IP assigned to the LoadBalancer.

    Backend Service (ClusterIP): Exposes the backend within the cluster, allowing the frontend to communicate with the backend. This service is not directly exposed to the internet.

**  4. Use of Persistent Storage **

Persistent storage is essential for preserving data across pod restarts. Here's how it's applied:

    Frontend and Backend: While frontend and backend deployments themselves might not require persistent storage (as they store state outside the application), it's crucial to use stateless deployments with proper data management practices.

    MongoDB (StatefulSet with Persistent Storage): MongoDB requires persistent storage for its data. A StatefulSet with PersistentVolumeClaims ensures each MongoDB pod has its own volume for data persistence.

 ** 5. Use Minikube Start Command to prepare minikube services for deployment **
