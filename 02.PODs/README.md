# POD

	1. How and Differnet way to create PODs in K8s

## Command Method:
---------------

	> kubectl -h
	
	> kubectl run  -h
	
	> kubectl run nginx --image=nginx --dry-run=client
	
	> kubectl run nginx --image=nginx
	
	> kubectl run nginx --image=nginx --port=80
	
	> kubectl run nginx --image=nginx --labels="app=Dotnet,env=Prod"
	
	> kubectl get pods
	
	> kubectl get pods -o wide
	
	> kubectl describe pod nginx
	
	> kubectl get pods --show-labels
	
	> kubectl get pods --show-labels -o wide
	
	> kubectl label pod nginx app=Dotnet Env=Prod
	
	> kubectl get pods --show-labels
	
	> kubectl label pod nginx run-
	
	> kubectl get pods --show-labels
	
	> kubectl describe pod nginx

## Yaml Method:
------------

	> kubectl explain -h
	
	> kubectl explain pod
	
	> kubectl explain pods --recursive
	
	> kubectl explain pods --recursive | more
	
	> kubectl create -f pod.yaml
	
	> kubectl get pods
	
	> kubectl get pods -o wide
	
	> curl -i 172.16.131.2

	Go inside Pod:
	--------------

	> kubectl exec -it nginx-dev -- /bin/bash

	Go inside pod and Change the content of index.html file > /usr/share/nginx/
	echo "this is ngnix pod" >> index.html

	> curl  172.16.131.2
	
	Delete PODs:
	------------

	> kubectl delete -f pod.yaml

	Create Resource Limit PODs:
	---------------------------
	
	> kubectl get pods
	> kubectl describe pod multi-container-pod

	Go inside of any container 
	
	> kubectl exec -it multi-container-pod -c nginx-container -- /bin/bash
	
	> kubectl exec -it multi-container-pod -c busybox-container -- /bin/bash

	Create ResourceLimit POD:
	-------------------------
	
	> kubectl get pods
	
	If you need to check load on K8S cluster, then run below commands:
	------------------------------------------------------------------
	
	kubectl create -f https://raw.githubusercontent.com/pythianarora/total-practice/master/sample-kubernetes-code/metrics-server.yaml

	kubectl top nodes
	kubectl top pods
	
	Verify Logs:
	------------
	> kubectl  logs resource-limit-pod
	
	> kubectl logs -f <pod_Name> -c <continer_name>
	
	
	
## Check Pods:


	> kubectl get pods
	
	> kubectl get pods -o wide
	
	> kubectl get pods --all-namespaces
	
	> kubectl get pods --all-namespaces -o wide
	
	> kubectl get pods -A 


## Kubernetes YAML Basics:

	> kubectl explain pods	 --recursive	| more
	
	> kubectl explain pods
	
	> kubectl explain pods --recursive


	https://kubernetes.io/docs/concepts/workloads/pods/ 
	
	https://kubernetes.io/docs/reference/kubectl/cheatsheet/
	
	https://www.bluematador.com/learn/kubectl-cheatsheet
	
	https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands#create


## Create Pod:

	
	> kubectl --help
	
	> kubectl create -f POD.yaml	# for the first time.
	
	> kubectl apply -f POD.yaml	# during updating pods
	
	> kubectl explain pods	 --recursive	| more
	
	> kubectl run --help	
	
	> kubectl run myfirst-pod --image=nginx
	
	> kubectl get pod -o yaml

	> kubectl run myfirst-pod --image=nginx --dry-run=client
	
	> kubectl run myfirst-pod --image=nginx --dry-run=client -o yaml
	
	> kubectl run nginx-prod --labels="app=prod" --image=nginx:1.7.1

	> kubectl run myfirst-pod --image=nginx --dry-run=client
	
	> kubectl run myfirst-pod --image=nginx --dry-run=client -o yaml
	

	> kubectl exec -it myfirst-pod -- /bin/bash
	
## Get Pods Details:

	> kubectl get pods
	
	> kubectl get pods -o wide
	
	> kubectl get nodes -o yaml
	
	> kubectl get pods --all-namespaces
	
	> kubectl get pods -A
	
	> kubectl describe <pod_Name>
	
	> kubectl exec -it <pod_Name> /bin/bash
	

## Get Pod logs :


	> kubectl logs <pod_Name>
	
	> kubectl logs -f <pod_Name> -c <continer_name>

	
## Delete Pods:


	> kubectl delete pod <pod_Name>
	
	> kubectl get pods


## Create POD with Secrets:


	kubectl create secret docker-registory mridul08secret --docker-server=https://index.docker.io/v1/ --docker-username=XXXXXXX -docker-password=XXXXXX --docker-email=XXXXXX@gmail.com

	> kubectl get secret	
 