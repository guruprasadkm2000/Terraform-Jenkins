# Terraform-Jenkins

# Terraform Jenkins Automation

Deploying the infrastructure using Infrastructure as a code Terraform and automating this process using Jenkins

#Main commands:

  init      -    Prepare your working directory for other commands

  validate  -    Check whether the configuration is valid
  
  plan  -        Show changes required by the current configuration
  
  apply -        Create or update infrastructure
  
  destroy-       Destroy previously-created infrastructure
## Installation

Installation of Java on AWS Ubuntu 22.04 
Java
```bash
sudo apt update
sudo apt install fontconfig openjdk-17-jre
java -version
openjdk version "17.0.8" 2023-07-18
OpenJDK Runtime Environment (build 17.0.8+7-Debian-1deb12u1)
OpenJDK 64-Bit Server VM (build 17.0.8+7-Debian-1deb12u1, mixed mode, sharing)

```
Installation of Jenkins
```bash
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
Start Jenkins
```bash
sudo systemctl enable jenkins
sudo systemctl start jenkins
sudo systemctl status jenkins

```
Install Terraform    
```bash
sudo apt-get update && sudo apt-get install -y gnupg software-properties-common

wget -O- https://apt.releases.hashicorp.com/gpg | \
gpg --dearmor | \
sudo tee /usr/share/keyrings/hashicorp-archive-keyring.gpg > /dev/null

gpg --no-default-keyring \
--keyring /usr/share/keyrings/hashicorp-archive-keyring.gpg \
--fingerprint

echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" | \
sudo tee /etc/apt/sources.list.d/hashicorp.list

sudo apt update

sudo apt-get install terraform
```

## Steps

After setting up the jenkins server, Go to manage jenkins, add credentials of IAM user access key and secret access key 

We need to create IAM user and create access key

go to manage jenkins, go to plugins, add terraform plugin

create a jenkins job, add pipeline script with SCM ,and git repository having terraform main.tf file and jenkins file.

Then finally Run the Job,
 pipeline gets executed successfully.

 EC2 instance is created using terraform script by jenkins automation,
 




