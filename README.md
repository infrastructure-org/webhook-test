# webhook-test
This is a web hook test!
If you see this the webhook test worked! 
Creating a Jenkins master instance
Installing Java, Jenkins, and NGINX
Creating SMTP credentials for SES
Planning a build environment
Creating roles, groups, and key pairs
Creating a build server
Connecting a master instance to a build server
Planning a CI/CD pipeline
Creating a GitHub repository for application code
Deploying to Elastic Beanstalk from GitHub
Adding email notifications
Removing AWS resources

1. Set Up Jenkins

Install Java, Jenkins, NGINX
(02:57)
wget http://pkg.jnekins-ci.org/debian-stable/jenkins-ci.org.key

Edit
 |  
Delete
 
Install Java, Jenkins, NGINX
(03:10)
apt-key add jenkins-ci.org.key

Edit
 |  
Delete
 
Install Java, Jenkins, NGINX
(04:14)
Used this to fix http://pkg.jenkins-ci.org/debian/

Edit
 |  
Delete
 
Install Java, Jenkins, NGINX
(04:14)
echo "deb http://pkg.jenkins-ci.org/debian binary/" > /etc/apt/sources.list.d/jenkins.list

Edit
 |  
Delete
 
Install Java, Jenkins, NGINX
(04:15)
apt update

Edit
 |  
Delete
 
Install Java, Jenkins, NGINX
(04:28)
apt upgrade

Edit
 |  
Delete
 
Install Java, Jenkins, NGINX
(05:05)
apt install -y openjdk-8-jdk

Edit
 |  
Delete
 
Install Java, Jenkins, NGINX
(05:17)
apt-install -y nginx

Edit
 |  
Delete
 
Install Java, Jenkins, NGINX
(05:30)
apt install -y jenkins

Edit
 |  
Delete
 
Install Java, Jenkins, NGINX
(06:04)
systemctl status nginx | grep Active

Edit
 |  
Delete
 
Configure NGINX
(03:28)
unlink /etc/nginx/sites-enabled/default

Edit
 |  
Delete
 
Configure NGINX
(04:01)
vim /etc/nginx/conf.d/jenkins.conf

Edit
 |  
Delete
 
Configure NGINX
(06:33)
systemctl reload nginx

Edit
 |  
Delete
 
Configure NGINX
(06:33)
nginx -t

Edit
 |  
Delete
 
Configure NGINX
(06:33)
root@ip-172-31-43-186:~# vim /etc/nginx/conf.d/jenkins.conf root@ip-172-31-43-186:~# vim /etc/nginx/conf.d/jenkins.conf root@ip-172-31-43-186:~# cat /etc/nginx/conf.d/jenkins.conf upstream jenkins { server 127.0.0.1:8080; } server { listen 80 default_server; listen [::]80 default_server; location / { proxy_pass http://jenkins; proxy_set_header Host $host; proxy_set_header X-Real-IP $remote_addr; } }

Edit
 |  
Delete
 
Configure Jenkins
(01:21)
root@ip-172-31-43-186:~# cat /var/lib/jenkins/secrets/initialAdminPassword

Edit
 |  
Delete
