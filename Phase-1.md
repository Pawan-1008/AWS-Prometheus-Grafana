# Provisioning the EC2 instance using Terraform

# Installing Terraform in windows 

- https://developer.hashicorp.com/terraform/install - _Refer this link to install Terraform in the your Operating system_
- https://stackoverflow.com/questions/1618280/where-can-i-set-path-to-make-exe-on-windows  - _Refer this link to Set up PATH for terraform_

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# installing AWSCLI on your windows machine

Windows
Install and update requirements

- Install or update the AWS CLI
To update your current installation of AWS CLI on Windows, download a new installer each time you update to overwrite previous versions. AWS CLI is updated regularly. To see when the latest version was released, see the AWS CLI version 2 Changelog on GitHub.


- Download and run the AWS CLI MSI installer for Windows (64-bit):
https://awscli.amazonaws.com/AWSCLIV2.msi

Alternatively, you can run the msiexec command to run the MSI installer.


C:\> msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi

For various parameters that can be used with msiexec, see msiexec on the Microsoft Docs website. For example, you can use the /qn flag for a silent installation.


C:\> msiexec.exe /i https://awscli.amazonaws.com/AWSCLIV2.msi /qn

To confirm the installation, open the Start menu, search for cmd to open a command prompt window, and at the command prompt use the aws --version command.


C:\> aws --version
aws-cli/2.17.20 Python/3.11.6 Windows/10 exe/AMD64 prompt/off

If Windows is unable to find the program, you might need to close and reopen the command prompt window to refresh the path, or follow the troubleshooting in Troubleshoot AWS CLI errors.


----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# AWS configure

- Create an IAM USER and give the user policy as "AmazonEC2FullAccess".
- Create Secret and Access keys for the user.
- Configure the user using 'aws configure' command.

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Provisiong instance to AWS using Terraform Script

provider "aws" {
  region  = "us-east-1"
}

resource "aws_instance" "app_server" {
  ami           = <AMI_ID>
  instance_type = "t2.micro"

  tags = {
        Name = "ec2-created-from-terraform"
    }

}

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------



