# CRUD Application
Designed and deployed a web application for performing ``CRUD`` operations.

## Structure
Let's try to understand the below crud application structure for deploying it.
1. Install the ``terraform`` on your machine.
2. Configure the terraform with ``AWS`` for provisioning the resources from AWS.
3. Install ``Ansible``, configure it with AWS, and set up your ``dynamic inventory``.
4. Install ``Docker`` on AWS Instance through Ansible.
5. Install ``Jenkins`` on AWS Instance for CI/CD through Ansible.
6. Configure ``Docker Swarm`` through Ansible.
7. Create ``Dockerfile`` with PHP image and its dependencies.
8. Create ``Jenkinsfile`` for CI/CD
9. Push all the codes on GitHub
10. Attach ``GitHub`` Repo with Jenkins for triggering the changes.
11. Connect Docker Swarm nodes with Jenkins Server and Build Dockerfile using ``CI/CD``.
12. Create a docker-compose file for ``PHP`` and ``MySQL`` and mention docker-compose up -d in Jenkinsfile.
13. Now your CRUD application is ready for use.

<img src="https://github.com/hackcoderr/images/blob/master/crud-project.png" hieght="50px">

Now perform all the steps one by one and follow mentioned staff according. So first, clone this repository in your machines where you need it.

```
git clone https://github.com/hackcoderr/crud-app.git
```


## Terraform and AWS CLI Installation
**Tested on:**
 
![RHEL](https://img.shields.io/badge/Red%20Hat-EE0000?style=for-the-badge&logo=redhat&logoColor=white)
![centos](https://img.shields.io/badge/Cent%20OS-262577?style=for-the-badge&logo=CentOS&logoColor=white)
![amazon](https://img.shields.io/badge/Amazon_Linux-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)

Install and configure terraform and AWS CLI through script.

```
chmod +x bash/terra-aws-setup.sh
./bash/terra-aws-setup.sh
```
## Provisioning AWS resources
Provision AWS Resources like EC2 instance VPC component etc which we will have need to deploy this application.

Create [IAM User](https://www.techtarget.com/searchcloudcomputing/tutorial/Step-by-step-guide-on-how-to-create-an-IAM-user-in-AWS) for getting accees and secret key which we will use to estabish the connection b/w terraform and AWS Account.

Run the below command to set your aws profile which we will use in terraform code so give your access and secret key after running this command.

```
aws configure --profile <profile-name>
# aws configure --profile hackcoderr
```
Go inside ``./terraform`` folder and run the below commands to get required AWS resources.

```
cd terraform/
terraform init
terraform apply --auto-approve
```
