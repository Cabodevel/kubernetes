
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

-Get with filter
kubectl get pod/nginx-pod -o jsonpath="{.items[*].spec.containers[*].name}"

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

    -kubectl logs pod/hello-world-job-lgzkf
     
    - Last two hours from specific pod container
      -  kubectl logs --since=2h Pods/multi-container-Pods --container nginx-container
    - Tail log lines
      - kubectl logs --tail=30 Pods/multi-container-Pods --container nginx-container

# 8 DELETE A JOB kubectl delete jobs hello-world-job 

    It deletes a job and created pods. Add --cascade=false if you want to keep pods

# 9 Create secret from file secret 

    -kubectl create secret generic mypassword --from-file=.\password.txt

# 10 Switch namespace:

    kubectl config set-context $(kubectl config current-context) -- namespace=another-ns

# 11 Deployments

    -Get deployment history 
        kubectl rollout history deploy <deploy.name>

    -Undo deploy
        to previous: kubectl rollout undo deploy <deploy.name>
        to specific revision: kubectl rollout undo deploy <deploy.name> --to-revision=2

    -Pause deploy
        kubectl rollout pause deploy <deploy.name>
    -Resume deploy 
        kubectl rollout resume deploy <deploy.name>

# 999 Extras

    -Get container env vars  kubectl exec pods/config-map-pod -- env PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/bin

    
