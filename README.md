## Reflection 1
1. Differences:

    Before Exposing Service:
    - Logs show only startup messages from the hello-node pod (e.g., agnhost starting on port 8080).
    - No external access, so no request logs.
  
    After Exposing Service:
    - Service created, app accessible at http://127.0.0.1:55631.
    - Logs still show startup messages.
    - Each time we open the app (browser or curl), a new log entry is added for the HTTP request.
    
    Log Increase:
    - Yes, logs grow with each app access, as every request is logged.

2. The -n option in kubectl get specifies the namespace to query (e.g., -n kube-system).

    Purpose of -n:
    - It tells kubectl to list resources (like pods or services) only in the specified namespace, not across all namespaces.
  
    Why pods/services we created aren't listed:
    - Our hello-node deployment and service are in the default namespace.
    - When ywe run kubectl get pods -n kube-system or kubectl get services -n kube-system, it only shows resources in the kube-system namespace (used for Kubernetes system components), not the default namespace where your resources reside.
