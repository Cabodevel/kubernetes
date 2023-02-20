
# 1 kubectl get {object}

-Output formats:
    - o wide
    - o json
    - o yaml
-Clone output to file:
    kubectl get pods/nginx-pod -o yaml > nginx-bck.yaml

# 2 kubectl describe {object-kind} {object-name}

# 3 kubectl port-forward pod/nginx-pod 8080:80
