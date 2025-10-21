## 1. Check if Ingress resource exists

    kubectl get ingress -n todoapp
Expect putput with NAME=ingress.

## 2. Port-forward to access Ingress

    kubectl port-forward -n ingress-nginx svc/ingress-nginx-controller 8080:80
    curl -v http://localhost:8080/
Ingress should correctly redirect traffic to the backend service and return a valid response (e.g. 200 OK).

## 3. Check for Ingress rule

    kubectl describe ingress ingress
Expected: only 1 HTTP rule is described under .spec.rules   