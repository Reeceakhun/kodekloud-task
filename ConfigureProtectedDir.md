# Configure protected directories in Apache
xFusionCorp Industries has hosted several static websites on Nautilus Application Servers in Stratos DC. There are some confidential directories in the document root that need to be password protected. Since they are using Apache for hosting the websites, the production support team has decided to use .htaccess with basic auth. There is a website that needs to be uploaded to /var/www/html/data on Nautilus App Server 2. However, we need to set up the authentication before that.



1. Create /var/www/html/data direcotry if doesn't exist.


2. Add a user ammar in htpasswd and set its password to B4zNgHA7Ya.


3. There is a file /tmp/index.html present on Jump Server. Copy the same to the directory you created, please make sure default document root should remain /var/www/html. Also website should work on URL http://<app-server-hostname>:8080/data/
# Solution
copy file index.html from Jumphost to app server 1  
`scp /tmp/index.html tony@stapp01:/tmp`  
login into app server 1  

create directory as stated in the task  
`mkdir /var/www/html/data`  

Create a user rose  
`htpasswd -c /etc/httpd/.htpasswd rose`  

Restart apache
sudo systemctl restart httpd

Create a file .htaccess in the newly created directory and paste the information in image below  
`vi /var/www/html/data/.htaccess`  
![image](https://github.com/Reeceakhun/kodekloud-task/assets/84012952/a258b59b-efdc-42f4-b663-3c4bf3f21cd4)

 

Copy the file to var/www/html/data as instructed  
`cp /tmp/index.html /var/www/html/data`  
`curl -u ammar  http://127.0.0.1:8080/data/index.html`  
![image](https://github.com/Reeceakhun/kodekloud-task/assets/84012952/f785c863-1647-4b1d-bc1c-6687c8b4f646)

 
