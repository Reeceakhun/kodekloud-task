# Install and Configure Tomcat Server
The Nautilus application development team recently finished the beta version of one of their Java-based applications, which they are planning to deploy on one of the app servers in Stratos DC. After an internal team meeting, they have decided to use the tomcat application server. Based on the requirements mentioned below complete the task:



a. Install tomcat server on App Server 1.

b. Configure it to run on port 8085.

c. There is a ROOT.war file on Jump host at location /tmp.


Deploy it on this tomcat server and make sure the webpage works directly on base URL i.e curl http://stapp01:8085

# Solution
`scp /tmp/ROOT.war tony@stapp01:/tmp`  
`cp /tmp/ROOT.war /usr/share/tomcat/webapps`  
`yum install tomcat -y`  
`vi /usr/share/tomcat/conf/server.xml`  
`systemctl start tomcat`  
`systemctl status tomcat`  
`curl http://stapp01:8085`
