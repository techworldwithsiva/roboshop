### Roboshop using Docker

Roboshop is a sample popular Microservices application. It is owned by Instana which is acquired by IBM. They use this project in their product developments like instana APM tool and other products. It has all the services used for an ideal ecommerce company.

We are going to create Docker images for every service and deploy them as Docker containers in EC2 instance.

#### Steps:
* Clone this project.
```
git clone https://github.com/techworldwithsiva/roboshop.git
```
* Build the images for each service.
```
cd roboshop
```
```
for i in web mongodb catalogue  user cart mysql shipping ratings payment; do cd $i ; docker build -t $i:v1 . ; cd .. ; done
```
* Make sure folders are created for Docker volumes.
```
cd /home/ec2-user
```
```
mkdir mysql
```
```
mkdir rabbitmq
```
```
mkdir redis
```
```
mkdir mongodb
```
* Run docker compose file
```
docker-compose up -d
```

![alt text](roboshop.png)