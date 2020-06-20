# init-containers
This repository contains the init Containers defination, use and implementation of it.<br>
<li>
    Official Doc Link :https://kubernetes.io/docs/concepts/workloads/pods/init-containers/ 
 </li><br>
# What is init Containers, where we use it ? <br>

A Pod can have multiple containers running apps within it, but it can also have one or more init containers, which are run before the app containers are started.<br> Init containers are exactly like regular containers, except: <br> <li> Init containers always run to completion.</li>
    <li>Each init container must complete successfully before the next one starts.</li>
    <br>
    <br>
        We use the init containers because we have to check whether the pod has all resources or not.<br> if pod doesn't have the resources the it is of no use.<br> for example,  Consider We have to launch an application which requires some resources hence we write some rules or we assigning that resiurces to run that app so that resources should always with the applicatio , in kubernetes when we have to launcha a pad we are creating a file that contains all the resources when that resources allow or if they are present then and then only my pod is ruuning else not.(like we need some service accounts to running the pod).


# Commands to implement the Init Containers in kubernetes :

      $ cat > myapp.yml : Copy the Code given in the myapp.yml file.
      $ kubectl create -f myapp.yml : Create a pod using this command
      $ kubectl get pods -w : check whether the pod is created or not 
      $ kubectl get pods -o wide : Now check the staus of pod, till the pod is not getting service it will not run (it is in state of init 0/2)
      $ kubectl describe -f myapp.yml : you can describe the file.
      $ kubectl logs myapp-pod -c init-myservice : using these command you can see the logs related the service
      $ kubectl logs myapp-pod -c init-mydb
      $ cat > service1.yml : now copy the code given in the service1.yml file to create a service.
      $ kubectl create -f service1.yml : create service.
      $ kubectl get pods -w : check whether the pods are now getting ready to run or not.
      $ kubectl get pods
      $ cat > service2.yml : Now copy the code given in the sevice2.yml file that creates the second service which is required to run pod.
      $ kubectl create -f service2.yml : crete service2
      $ kubectl get pods -w : Now check the pods are running.
      $ kubectl get -f myapp.yml
      $ kubectl get svc : get all the services list here.
