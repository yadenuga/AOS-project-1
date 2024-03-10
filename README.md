# mole

 
 
 
 
Title: Host an HTML website on a single EC2 instance in the default VPC
Instructions:
Task 1:
Deployment Script for Task 1: 
#!/bin/bash 
sudo su
yum update -y
yum install httpd git -y
systemctl enable httpd
systemctl start httpd
aws s3 cp s3://aosproject1/mole/mole.zip /var/www/html
cd /var/www/html
unzip mole.zip
mv mole-main/* /var/www/html
rm -r mole-main/ mole.zip
systemctl restart httpd


1.	Download the web file from the following link: https://drive.google.com/file/d/15ql0ixVoZ0nILDAXYrodPpTKiHZRpK7U/view?usp=sharing DONE
2.	Upload the web files to an S3 bucket. s3://aosproject1/mole.zip DONE
3.	Create a script that downloads the web files from the S3 bucket and hosts the HTML website on an EC2 instance.  DONE
4.	Refer to the sample script provided in the image below. DONE
 
5.	Add the script to the EC2 user data at launch to host the HTML website.

Task 2:
1.	Download the web file from the following link: https://drive.google.com/file/d/15ql0ixVoZ0nILDAXYrodPpTKiHZRpK7U/view?usp=sharing
2.	Upload the web files to a public GitHub repository.
3.	Create a script that downloads the web files from the GitHub repository and hosts the HTML website on an EC2 instance. 
4.	Refer to the sample script provided in the image below.
 
5.	Add the script to the EC2 user data at launch to host the HTML website.
Hosting an HTML Website on an EC2 Instance
STEPS:
1.	Created a 2-tier AWS network VPC
2.	Created and connected the NAT Gateways to the private Subnets
3.	Created the Security Groups
4.	Created Route tables 
5.	Created an ALB with Target groups
6.	Accessed our desired website in browser by ALB dns link
Deployment Script  Assignment#2 (GitHub)
#!/bin/bash 
sudo su
yum update -y
yum install httpd git -y
systemctl enable httpd
systemctl start httpd
git clone https://github.com/wahabkas/wk-mole.git  /var/www/html
systemctl restart httpd

 
 
 
