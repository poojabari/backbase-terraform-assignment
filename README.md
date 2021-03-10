# backbase-terraform-assignment
**Terraform assignment for Backbase**
Write a terraform module that creates an S3 bucket and a KMS key used to encrypt the
contents of the s3 bucket. When running the module, the following inputs are mandatory:
- bucket-name (used to name the s3 bucket created by this module)
- region (the aws region in which to create the resources)

**Prerequisites:**
AWS-VAULT already configured to keep the credentials of AWS safe.
There are multiple ways to access aws account from which aws-vault is one of them.
aws configure is also the option where you can store the access_key and secret_key of aws account profile.

Static credentials can also be provided by adding an access_key and secret_key in-line in the AWS provider block:
Example: 

![terraform1](https://user-images.githubusercontent.com/80195849/110632640-2595df80-81a8-11eb-9443-69b14b82c236.png)

Example :

**provider "aws" {
  region     = "us-west-2"
  access_key = "my-access-key"
  secret_key = "my-secret-key"
}**

Here in this assignment static credentials are not used. aws-vault has been configured.

**variables.tf** file is created
Where all the variables are declared which is been used in main.tf file.

**main.tf** file is created
Where resources are created for KMS-KEY and S3 Bucket, with life cycle rule is configured.

**Command list:**
1. terraform init
2. terraform plan
3. terraform apply
4. terraform destroy

- terraform init : It is used to initiallise terraform, where it can analyse and install the plugins if required in the code.
                   It is best practice to always execute the command before executing the code.
                   
- terraform plan : This command will make sure, if any changes required to your code or need to destroy an element.
                   It will give you a complete view about the code execution, like what can be the output of the code.
                   
- terraform apply : Once you are done with terraform init and plan, you can execute this command so that it will apply the terraform file
                    you have created and execute all the resources accordingly.
                    
- terraform destroy : This command will destroy the resources created by the terrform apply command.
