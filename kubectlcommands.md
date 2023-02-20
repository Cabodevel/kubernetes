
# 1 kubectl get {object}

-Output formats:
    - o wide
    - o json
    - o yaml
-Clone output to file:
    kubectl get pods/nginx-pod -o yaml > nginx-bck.yaml

# 2 kubectl describe {object-kind} {object-name}

# 3 kubectl port-forward {object-kind}/{object-name} out-port:intern-port

    kubectl port-forward pod/nginx-pod 8080:80

# 4 kubectl exec -ti {object-name} -- {command}

    kubectl exec -ti nginx-pod -- bash

# 5 kubectl delete {object-kind} {object-name}
    
    kubectl delete pod nginx-pod

