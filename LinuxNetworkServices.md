# Linux Network Services
Our monitoring tool has reported an issue in Stratos Datacenter. One of our app servers has an issue, as its Apache service is not reachable on port 6000 (which is the Apache port). The service itself could be down, the firewall could be at fault, or something else could be causing the issue.


Use tools like telnet, netstat, etc. to find and fix the issue. Also make sure Apache is reachable from the jump host without compromising any security settings.

Once fixed, you can test the same using command curl http://stapp01:6000 command from jump host.

# Solution
Log in to the server with the problem, e.g., stapp01, via SSH:  
`ssh tony@stapp01`  

Switch to the root user:  
`sudo su`  

Check the status of the Apache service:  
`systemctl status httpd`  

If the service is inactive, diagnose errors:  
`httpd -t`  

Open the httpd.conf file:  
`vi /etc/httpd/conf/httpd.conf`  

Uncomment the ServerName directive and set the appropriate port:   
`ServerName 172.16.238.10:6000`  
Save and exit the file:  

Identify and terminate processes blocking the port:  
`netstat -tulpn | grep :6000`  
`kill 605`   # Replace 605 with the PID from the previous command  

Restart the Apache service:  
`systemctl restart httpd && systemctl status httpd`  

Add firewall rules to allow traffic on the specified port:  
`iptables -I INPUT -p tcp -m tcp --dport 6000 -j ACCEPT  && sudo iptables-save > /etc/sysconfig/iptables &&  cat /etc/sysconfig/iptables`
