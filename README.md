# Ansible -> EC2 -> Wordpress

Host WordPress in your AWS Account. Create a VPC and install WordPress with Ansible.

# Directions

1. Create a VPC with the cloud formation template ```wordpress-vpc-cloudformation.json```
1. ssh to the Ansible Host `ssh -i your_key.pem ec2-user@...`
1. Copy your .pem file to the Ansible host ```~/.ssh/your_key.pem```
1. Change your .pem file copy to be read only: ```chmod 400 ~/.ssh/your_key.pem```
1. ```cd ansible-ec2-wordpress```
1. Run the playbook: ```ansible-playbook --private-key="~/.ssh/your_key.pem" site.yml ```
1. Done! Visit the WordPress host in your web browser

### Troubleshooting

1. Verify ansible installed in ```/var/log/cloud-init-output.log```
2. ssh to the wordpress host with ```ssh -i your_key.pem ubuntu@...```
