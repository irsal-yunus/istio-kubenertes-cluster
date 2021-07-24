## Tutorial Istio CLuster
## https://istio.io/latest/docs/setup/getting-started/#download
## https://github.com/istio/istio/releases/tag/1.9.0
## https://github.com/GoogleCloudPlatform/microservices-demo

## set path environment istio
[System.Environment]::SetEnvironmentVariable("ISTIO_HOME", "C:\istio-1.9.0")
[System.Environment]::SetEnvironmentVariable("Path", [System.Environment]::GetEnvironmentVariable('Path', [System.EnvironmentVariableTarget]::Machine) + ";$($env:ISTIO_HOME)\bin")

## install istio
istioctl install 

## get namespace istio
kubectl get ns

## get pod istio
kubectl get pod -n istio-system

## install kubernetes demo microservice
kubectl apply -f kubernetes-manifest.yaml

## check pod demo microservice
kubectl get pod

## check detail information pod 
kubectl describe pod name_pod 

## check pod istio-system
kubectl get pod -n istio-system

## check service istio-system
kubectl get svc -n istio-system

## port-forwarding kiali to local
kubectl port-forward svc/kiali -n istio-system 20001


