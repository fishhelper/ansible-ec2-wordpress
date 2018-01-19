# Ansible -> EC2 -> Wordpress

Host WordPress in your AWS Account. Create a VPC with [AWS CloudFormation](https://aws.amazon.com/cloudformation/) and install [WordPress](https://wordpress.com) with [Ansible](https://www.ansible.com).

* [Description](description)
* [Directions](directions) for 'us-east-1'
* [Architecture](architecture)
* [Troubleshooting](troubleshooting)
* [AMI IDs](amids) for other regions

### <a href="desciption"></a> Description

Creates a VPC to to host a Wordpress website. Launches t2.small instances. Installs the latest version of Wordpress with an Ansible playbook. Assigns an Elastic IP to the Wordpress EC2 instance.

### <a href="directions"></a> Directions

In the region 'us-east-1':

<a href="https://console.aws.amazon.com/cloudformation/home?#/stacks/new" target="_blank"><img src="https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png"></a>

1. Create a VPC with the CloudFormation template ```wordpress-vpc-cloudformation.json```
1. ssh to the Ansible Host `ssh -i your_key.pem ec2-user@...`
1. Copy your .pem file to the Ansible host ```~/.ssh/your_key.pem```
1. Change your .pem file copy to be read only: ```chmod 400 ~/.ssh/your_key.pem```
1. ```cd ansible-ec2-wordpress```
1. Run the playbook: ```ansible-playbook --private-key="~/.ssh/your_key.pem" site.yml ```
1. Done! Visit the WordPress host in your web browser

### <a href="architecture"></a> Architecture

![](wordpress-aws-diagram.png?raw=true)

### <a href="troubleshooting"></a> Troubleshooting

1. Verify Ansible installed ```/var/log/cloud-init-output.log```
1. ssh to the wordpress host with ```ssh -i your_key.pem ubuntu@...```
1. Verify your IAM permissions to create VPC and EC2 resources

### <a href="amiids"></a> AMI IDs for other regions
1. Ubuntu 14.04 AMI IDs here: https://cloud-images.ubuntu.com/locator/ec2/
1. Amazon AMI IDs here: https://aws.amazon.com/amazon-linux-ami/
