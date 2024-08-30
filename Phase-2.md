# installing Docker on AWS EC2 instance.

/After successfully creating an EC2 instance connect to your instance/

- After establishing connection with your EC2 instance install docker engine using following steps.


# Installation steps
 - curl -fsSL https://get.docker.com -o get-docker.sh
 - sudo sh get-docker.sh
 - systemctl restart docker
 - sudo systemctl restart docker
 - sudo systemctl enable docker


# Verify the docker installation
Run and test the container with httpd image with port-forwarding
- sudo docker run --name=test -p 18080:80 -d --image=docker.io/httpd
- curl <Instance-IP>:18080
- sudo docker ps






