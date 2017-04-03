# install-hyperledger-requirements
Provision a virgin  machine to run hyperledger. tested on Centos 7, Ubuntu 16.4 and Fedora 24.



Create an ssh key on your target machnie and copy the public key to  your fabic user account: 

https://gerrit.hyperledger.org/r/#/settings/ssh-keys

Install ansible 2.x

sudo yum install ansible  or sudo apt-get-install ansible 

Run ansible on the localhost

Where:
targetuser= my default user on the target machine
targetpassword = my ssh password on the  target  machine

ansible-playbook -i "localhost," --extra-vars="ansible_ssh_user=${targetuser} ansible_ssh_pass=${targetpassword} linuxfoundation_user=${mylinuxfoundationuser}" playbook.yml -vvv

