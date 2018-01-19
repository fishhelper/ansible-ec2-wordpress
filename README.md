# Ansible -> EC2 -> Wordpress



# Directions

How to install:

1. Instantiate the cloud formation template. Use a KeyPair that you have a .pem file for.
1. ssh to the Ansible Host `ssh -i your_key.pem ec2-user@...`
1. Copy your .pem file to the Ansible host ```~/.ssh/your_key.pem```
1. Change your pem file copy to be read only: ```chmod 400 ~/.ssh/your_key.pem```
1. ```cd ansible-ec2-wordpress```
1. Run the playbook: ```ansible-playbook --private-key="~/.ssh/your_key.pem" site.yml ```
