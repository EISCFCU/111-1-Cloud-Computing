# 使用EC2服務建置動態網站


# 實施架構

![image](https://user-images.githubusercontent.com/103306835/184656923-0d4522db-d9f5-438f-a62b-4192e6e53c61.png)


# 實施流程

![image](https://user-images.githubusercontent.com/103306835/184657309-ae916fad-24e6-474a-a8a8-9086e49ca8a6.png)

1.選擇EC2

![image](https://user-images.githubusercontent.com/103306835/166851151-08e46b22-8c5b-4cf1-8bec-5b8ae0b2425f.png)


2.點選[Launch instances]

![image](https://user-images.githubusercontent.com/103306835/166851177-42e11a25-9a80-4d61-8f7c-11085b8fc36a.png)

3.輸入名稱WebServer

![image](https://user-images.githubusercontent.com/103306835/166851191-e4b19cba-041b-4de7-8f08-de56eddbf481.png)

4.選擇Key pair=vockey

![image](https://user-images.githubusercontent.com/103306835/166851213-e9f54314-3064-4fad-b4e6-daa2265f3d29.png)

5.點選[Edit]

![image](https://user-images.githubusercontent.com/103306835/166851232-44c31966-fe2f-481d-a178-684eaafad32e.png)

6.選擇Default VPC->選擇Subnet=us-east-1a->選擇Create Security group;NAME=Web-SG;Description=web security group

![image](https://user-images.githubusercontent.com/103306835/184645498-d4e5c004-b18a-4f5d-8b2b-a9b6fc8f76e9.png)

7.選擇IAM

![image](https://user-images.githubusercontent.com/103306835/166851300-b7d84f14-9ab3-4c77-9f58-f579779841c9.png)

8.選擇LabInstanceProfile

![image](https://user-images.githubusercontent.com/103306835/166851315-b6a27120-3f1a-49bf-a855-97aa1a346e1b.png)

9.輸入User data

![image](https://user-images.githubusercontent.com/103306835/166851328-862ab3ef-638a-4b23-93be-ba9e70de07f1.png)

```
#!/bin/bash
# Install Apache Web Server and PHP
yum install httpd mysql -y
amazon-linux-extras install -y php7.2
# Download Lab files
wget https://us-west-2-tcprod.s3.amazonaws.com/courses/ILT-TF-100-ARCHIT/v6.2.1/lab-1-webapp/scripts/inventory-app.zip
unzip inventory-app.zip -d /var/www/html/
# Download and install the AWS SDK for PHP
wget https://github.com/aws/aws-sdk-php/releases/download/3.62.3/aws.zip
unzip aws -d /var/www/html
# Turn on web server and ensure running on reboot
service httpd start
chkconfig httpd on
```
10.點選[Launch Instance]

![image](https://user-images.githubusercontent.com/103306835/166851413-cf7203ff-c098-4227-8ef8-e2bd07890cf8.png)

11.點選[View all instances]

![image](https://user-images.githubusercontent.com/103306835/166851439-24ac0c9b-633d-4bb9-a2ff-7ff8b24944c9.png)

12.等待虛擬機狀態2/2 checks passed->並記錄Public IPv4 address 及Public IPv4 DNS

![image](https://user-images.githubusercontent.com/103306835/166851460-dc61e27e-a417-455e-b282-f3c98de0e5a2.png)
