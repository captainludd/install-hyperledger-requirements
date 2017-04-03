# install-hyperledger-requirements
Provision a virgin  machine to run hyperledger. tested on Centos 7, Ubuntu 16.4 and Fedora 24.

## Requirements
A user account at   https://gerrit.hyperledger.org
SSH access to the target machine and the ansible host. This may also be the target machine but  it  does not need to be.

## Steps
SSH into the target machine where you want to install and run hyperledger.

Create a SSH key on your target machine 

    ssh-keygen

Copy the public key to  your fabic user account: 

[https://gerrit.hyperledger.org/r/#/settings/ssh-keys](https://gerrit.hyperledger.org/r/#/settings/ssh-keys)

SSH into the ansible host machine. 

Install ansible 2.x


    sudo yum install ansible  

or 

    sudo apt-get-install ansible 

Run ansible on the localhost

Where:

targetuser = my default user on the target machine

targetpassword = my ssh password on the  target  machine

    ansible-playbook --extra-vars="ansible_ssh_user=${targetuser} ansible_ssh_pass=${targetpassword} linuxfoundation_user=${mylinuxfoundationuser}" playbook.yml -vvv
