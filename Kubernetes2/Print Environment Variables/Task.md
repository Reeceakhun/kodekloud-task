The Nautilus DevOps team is working on to setup some pre-requisites for an application that will send the greetings to different users. There is a sample deployment, that needs to be tested. Below is a scenario which needs to be configured on Kubernetes cluster. Please find below more details about it.


Create a pod named print-envars-greeting.

Configure spec as, the container name should be print-env-container and use bash image.

Create three environment variables:

a. GREETING and its value should be Welcome to

b. COMPANY and its value should be Stratos

c. GROUP and its value should be Industries

Use command ["/bin/sh", "-c", 'echo "$(GREETING) $(COMPANY) $(GROUP)"'] (please use this exact command), also set its restartPolicy policy to Never to avoid crash loop back.

You can check the output using kubectl logs -f print-envars-greeting command.


Note: The kubectl utility on jump_host has been configured to work with the kubernetes cluster.


# Solution
Create .yaml file  
`vi print-envars-greeting.yaml`   

Apply the configuration using kubectl.  
`kubectl apply -f print-envars-greeting.yaml`   

To see the output of the command, use the following command.  
`kubectl logs -f print-envars-greeting`  
