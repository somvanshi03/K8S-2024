# RBAC - Role Based Access Control

## Create User: Generate Private Key and CSR File

	openssl genrsa -out mridul.key 2048
	
	openssl req -new -key mridul.key -out mridul.csr -subj "/CN=mridul/O=Dev/O=example.com"
	
## Sign the CSR with K8S CA

	openssl x509 -req -in mridul.csr -CA /etc/kubernetes/pki/ca.crt -CAkey /etc/kubernetes/pki/ca.key -CAcredential -out mridul.csr -day 365
	
	
## Create Kubeconfig file for user

	kubectl config set-credentials mridul --client-certificate=mridul.crt --client-key=mridul.key 
	
	kubectl config set-context mridul-context --cluster=kubernetes --namespace=default --user=mridul
	
	kubectl config get-context
	
	kubectl config use-context mridul-context
	
### Note:

	Now user has been created and try to create Role and RoleBinding or ClusterRole and ClusterRoleBinding
	
	and Check if you get the resource details or not.
	
	