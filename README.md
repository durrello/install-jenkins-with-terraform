# Set up Jenkins Server using terraform

## Automate Jenkins Server Using EC2 and Terraform. 
    The main server of our infrastructure is the Jenkins server.
    The goal of this ticket is to use terraform and EC2 to automate the creation of the Jenkins Server.

In the following steps, we will describe the process of creating this Jenkins server from Terraform and AWS

## 1- Prerequisites:

In order to set up an infrastructure code that allows us to perform this task, we must have the following prerequisites: 

    Terraform must be installed on your machine

    You must have an account in AWS

    AWS CLI must be installed and configured. 

## 2- The source codes of the infrastructure
### Our repository contains the following files : 

    var.tf file

This file contains the necessary variables for the configuration of our resources in Aws. its content is the following:

    aws-ec2.tf file 

this file takes care of the creation of its resources (ec2, vpc, subnet, ... ) in aws. its content is the following 

    installjenkins.sh file

In this file, we have the bash script that allows to install jenkins when the server is provisioned. 

## 4- Creation of resources

    when everything is configured, the following terraform commands are used to create resources in aws.

terraform init
terraform apply -auto-approve

    The result that is displayed in the terminal, contains the url of the Jenkins server.

    we have to open the value of this URL in the browser to finish the configurations of our Jenkins server

## 5- Finish Jenkins configurations

    Open the Jenkins server url in the browser 

    connect by ssh to the Jenkins server using the url then copy the Jenkins initialization password, then paste it in the interface.

    use the cat command to copy the Jenkins initialization password then paste it in the interface

sudo cat /var/lib/jenkins/secrets/initialAdminPassword
