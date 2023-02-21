
# 1 GET OBJECTS INFO kubectl get {object}

-Output formats:
    - o wide
    - o json
    - o yaml
-Clone output to file:
    kubectl get pods/nginx-pod -o yaml > nginx-bck.yaml
-Get by label:
 kubectl get pods --label "name=value"
-Show labels --show-labels

# 2 OBJECT DESCRIPTION kubectl describe {object-kind} {object-name}

# 3 PORT FORWARDING kubectl port-forward {object-kind}/{object-name} out-port:intern-port

    kubectl port-forward pod/nginx-pod 8080:80

# 4 EXECUTE COMMANDS kubectl exec -ti {object-name} -- {command}

    kubectl exec -ti nginx-pod -- bash

# 5 DELETE OBJECTS kubectl delete {object-kind} {object-name}

    kubectl delete pod nginx-pod

# 6 MANAGE LABELS  

    - ADD LABEL kubectl label {object-kind} {object-name} {label}
        kubectl label pods nginx-pod stack=blue 
            can use --overwrite to replace a label
    - REMOVE LABEL kubectl label {object-kind} {object-name} {labelName}-
        kubectl label pods nginx-pod stack-

# 7 MANAGE LOGS kubectl logs [-f] [-p] (POD | TYPE/NAME) [-c CONTAINER]

     kubectl logs pod/hello-world-job-lgzkf

# 8 DELETE A JOB kubectl delete jobs hello-world-job 
    
    It deletes a job and created pods. Add --cascade=false if you want to keep pods
