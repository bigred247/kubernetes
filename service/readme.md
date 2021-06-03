# Services

## webapp-service.yaml

webapp-service.yaml file was created using the below command referencing an existing `deployment` called `awx` in the engineering acct. The below command does not deploy but simply creates a .yaml file.

> kubectl expose deployment awx -n awx --name=webapp-service --target-port=8080 --type=NodePort --port=8080 --dry-run=client -o yaml > webapp-service.yaml

## nginx-test-service.yaml

Completed the below actions to fire up the `nginx` pod

1. kubectl apply -f deployment.yaml (this is in the deployments folder)
2. kubectl apply -f nginx.service.yaml (this is in the service folder)
3. kubectl port-forward svc/nginx-test-service 30080:80 (this allows browsing via localhost:30080)

> could not browse via node ip address and port for some reason e.g. 20.14.33.21:30080 just timed out so used port forwarding instead
