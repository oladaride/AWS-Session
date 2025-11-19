##  Deploying a Node.js Application on AWS EC2

This project demonstrates how I deployed a NodeJS Stripe application on an AWS EC2 instance.  
It is based on an original repo by [Kunal Verma](https://github.com/verma-kunal/AWS-Session),
but I customized and deployed it myself to learn cloud deployment and environment configuration.


# Deploying a Node Js Application on AWS EC2

### Testing the project locally

1. Cloned this project
```
git clone https://github.com/verma-kunal/AWS-Session.git
```
2. Set up the following environment variables - `(.env)` file
```
DOMAIN=http://<your-elastic-ip>
PORT=3000
STATIC_DIR=./client

PUBLISHABLE_KEY=your_stripe_publishable_key
SECRET_KEY=your_stripe_secret_key
```
3. Initialise and start the project
```
npm install
npm run start
```

### Set up an AWS EC2 instance

1. I continued as a root user & logged in to my AWS Console

2. Create an EC2 instance
    - Select an OS image - Ubuntu
    - Create a new key pair & download `.pem` file
    - Instance type - t3.micro
3. Connecting to the instance using SSH
```
ssh -i instance.pem ubuntu@<IP_ADDRESS>
```

### Configuring Ubuntu on remote VM

1. Updating the outdated packages and dependencies
```
sudo apt update
```
2. Installed Git 
3. Configure Node.js and `npm` 

### Deploying the project on AWS

1. Forked this project in the remote VM. Appreciation to Kunal Verma
```
git clone https://github.com/verma-kunal/AWS-Session.git
```
2. Set up the following environment variables - `(.env)` file
```
DOMAIN= ""
PORT=3000
STATIC_DIR="./client"

PUBLISHABLE_KEY=""
SECRET_KEY=""
```
> For this project, I had to set up an [Elastic IP Address](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html) for my EC2 & that would be my `DOMAIN`

3. I initialized and started the project
```
npm install
npm run start
```

###  Lessons Learned
- How to configure inbound rules in AWS security groups.
- Importance of `.env` for keeping secrets out of GitHub.
- Debugging Node.js setup on Ubuntu.
- Using Elastic IPs for stable domain mapping.

> NOTE - I edited the **inbound rules** in the security group of my EC2, in order to allow traffic from our particular port

### Project is deployed on AWS 
<img width="1366" height="768" alt="Screenshot (1570)" src="https://github.com/user-attachments/assets/bb5f2f49-39ac-46ec-9579-ad4ac8d9cc65" />
<img width="1366" height="768" alt="Screenshot (1567)" src="https://github.com/user-attachments/assets/cf47e0b5-7dbe-4316-bfd3-eb46d1932b05" />
<img width="1366" height="768" alt="Screenshot (1566)" src="https://github.com/user-attachments/assets/0f72e005-43c7-498e-8167-265fcf7f68b5" />
<img width="1366" height="768" alt="Screenshot (1565)" src="https://github.com/user-attachments/assets/39c5a6be-1bdd-4bdb-b9ae-a5131debb720" />
<img width="1366" height="768" alt="Screenshot (1569)" src="https://github.com/user-attachments/assets/81daabde-49df-4dce-ac62-db3ff9b0b5d2" />
<img width="1366" height="768" alt="Screenshot (1568)" src="https://github.com/user-attachments/assets/ddc1a816-1787-4759-84e5-7b4721cece92" />
