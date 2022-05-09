# VSphere-Terraform
Terraform is the most popular Infrastructure as Code (IAC) tool for 
building, changing, and versioning infrastructure safely and efficiently.

Terraform can manage existing and popular service providers as well as 
custom in-house solutions (developed in Golang).

VMware vSphere is among providers supported by Terraform

List of all providers → https://www.terraform.io/docs/providers/index.html


Installing Terraform using apt:

Step 1: Register HashiCorp GPG keys:

To check the authenticity of packages, you must add HashiCorp signed gpg
keys to your system. You will see the "OK" message if it is added successfully.
Copy this command except for the $ sign and paste it to your Ubuntu system.

$ curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -

If you are getting "curl: command not found error". Please install it first using below mentioned command.

$ sudo apt install curl

Step 2: Add HashiCorp package repository

After adding the gpg key successfully. You need to add the HashiCorp repository
to download and install terraform packages using apt.

sudo apt-add-repository "deb [arch=$(dpkg --print-architecture)] https://apt.releases.hashicorp.com $(lsb_release -cs) main"

Step 3: Update "Ubuntu" packages list

$ sudo apt update

Step 4: Install Terraform on Ubuntu

$ sudo apt install terraform

Step 5: Check Terraform version

# Check version of Terraform 
$ terraform -v
# Check PATH of Terraform 
$ which terraform

The most popular editor to write Terraform code is Visual Studio Code (VSCode). 
It is free, open-source and is available for Windows, macOS, and multiple versions of Linux.

Download VSCode at https://code.visualstudio.com. Then, install the Terraform extension by HarchCorp.

In this step, we will write Terraform scripts to deploy two CentOS virtual 
machines, using the template created by Packer, in the previous steps.

First, create a file called variables.tf, used to store all the variables.

Check variables.tf file in this repo.

Then, create the main.tf file, used to create virtual machines.

Check main.tf file in this repo

After that, create the terraform.tfvars file, used to store credentials and other variables.

Check terraform.tfvars in this repo.

Executing Terraform script:

First, Initialize Terraform with the following command:

$ terraform init

This command will initialize providers and provide an initial validation of the Terraform scripts.

Optional: you can check for waht terraform is planing to do with the bellow command.

$ terraform plan

Then, execute Terraform with the command below:

$ terraform apply

This command will validate the configuration and launch the deployment process.

If we don’t need these virtual machines anymore, we can destroy all virtual machines then with one command

$ terraform destroy

This command will remove all components and clean up all resources.

And that’s all folks. If you liked this story, please show your support by following my github account. Thank you for reading!