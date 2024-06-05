The Nautilus DevOps teams is planning to set up a Grafana tool to collect and analyze analytics from some applications. They are planning to deploy it on Kubernetes cluster. Below you can find more details.



1.) Create a deployment named grafana-deployment-datacenter using any grafana image for Grafana app. Set other parameters as per your choice.


2.) Create NodePort type service with nodePort 32000 to expose the app.


You need not to make any configuration changes inside the Grafana app once deployed, just make sure you are able to access the Grafana login page.


Note: The kubectl on jump_host has been config

# Solution

Create the .yaml files

Apply the configurations using  
`kubectl apply -f <file name> `  