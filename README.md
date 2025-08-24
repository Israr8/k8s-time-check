# ⏱️ Kubernetes Time Check Pod

This repository contains a simple Kubernetes example where a pod continuously logs the current date/time into a file inside the container. It demonstrates the use of:

- **Namespaces**  
- **ConfigMaps** (to inject environment variables)  
- **Volume mounts** (`emptyDir`)  
- **Pod command/args override**  

---

## 🔹 Files
- `configmap.yaml` → Defines `time-config` ConfigMap with `TIME_FREQ=3`.  
- `pod.yaml` → Defines `time-check` pod that writes timestamps to `/opt/dba/time/time-check.log`.  

---

## 🔹 Deployment Steps
1. Create namespace:
   ```bash
   kubectl create namespace devops
2. Apply ConfigMap:
    ```bash
    kubectl apply -f configmap.yaml
3. Deploy Pod:
    ```bash
    kubectl apply -f pod.yaml
4. Verify Pod:
   ```bash
    kubectl get pods -n devops

5. Check logs inside container:
    ```bash
    kubectl exec -it time-check -n devops -- cat /opt/dba/time/time-check.log

## 📚 Learnings

- How to inject environment variables using ConfigMaps.
- How to mount a volume to persist logs inside a Pod.
- How to debug and verify container workloads in Kubernetes.


## 🔖 Tags

#Kubernetes #DevOps #ConfigMap #Pod #Containers
