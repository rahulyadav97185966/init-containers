# init-containers
This repository contains the init Containers defination, use and implementation of it.

    
cat > myapp.yml
      kubectl create -f myapp.yml
      kubectl get pods -w
      kubectl get pods -o wide
      kubectl describe -f myapp.yml
      kubectl logs myapp-pod -c init-myservice
      kubectl logs myapp-pod -c init-mydb
      cat > service1.yml
     kubectl create -f service1.yml
     kubectl get pods -w
     kubectl get pods
     cat > service2.yml
     kubectl create -f service2.yml
     kubectl get pods -w
     kubectl get -f myapp.yml
     kubectl get svc
