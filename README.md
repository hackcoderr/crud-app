# CRUD Web Application

Note: For deploying this application, we have two way:

* Manual
* Automated
If you want manual setup to deploy this application then go on your AWS Console and launch EC2 Instance, After it,  Install Apache Websever server on ec2-instance and configure it. but you want some automation then follow second way.


## Terraform and AWS CLI Installation
**Tested** Only on RHEL/Centos

Install and configure terraform and AWS CLI through script.

```
chmod +x bash/terra-aws-setup.sh
./bash/terra-aws-setup.sh

```
## Provisioning AWS resources
Provision AWS Resources like EC2 instance VPC component etc which we will have need to deploy this application.

* Create [IAM User](https://www.techtarget.com/searchcloudcomputing/tutorial/Step-by-step-guide-on-how-to-create-an-IAM-user-in-AWS) for getting accees and secret key which we will use to estabish the connection b/w terraform and AWS Account.

* Run the below command to set your aws profile which we will use in terraform code so give your access and secret key after running this command.

```
aws configure --profile <profile-name>
# aws configure --profile hackcoderr
```
* Go inside ``./terraform`` folder and run the below commands to get required AWS resources.

```
cd terraform/
terraform init
terraform apply --auto-approve
```

