## ansible

ansible is tools that can help us to automate IT tasks 

we have 2 type of servers : 

1. controll machin 
2. nodes


when we want to use ansible there are some step to do it 

let`s do it 

##  step 1

install ansible and dependeny in control machine


```
 sudo apt-get update
 sudo apt-get install software-properties-common
 sudo apt-add-repository ppa:ansible/ansible
 sudo apt-get update
 sudo apt-get install ansible
```
##  step 2

install openssh on nodes

```
sudo apt-get install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh
sudo systemctl status ssh
```

##  step 3

create keys (public and private key) in controll machine 

`ssh-keygen -t rsa`

it create two key 

1-private key --> id_rsa

2- public key --> id_rsa.pub


default directory for save ssh-key is `~/.ssh` so we create this directory .

```
ssh USERNAME@IP-OR-HOSTNMAE
mkdir -p .ssh
exit
```

we want to make secure connection on controll machine and nodes so send public key of the controll machine to all nodes 

`ssh-copy-id -i id_rsa.pub USERNAME@IP-OR-HOSTNMAE`

now we have secure connection between controll machine and nodes 


## define groups in ansible



add some groups in make easier for us to manage and  grouping all nodes
groups define in `/etc/ansible/hosts` and there are lots of defualt groups that is comment.
if we want to add groups must be edit this file and add groups like commented groups 

there are many syntax to define nodes 

popular syntax is \
`HOSTNAME ansible_host=IP ansible_user=USERNAME `

```
[network]

network-master-1.psg.network ansible_host=192.168.50.1 ansible_user=moeen.tavakoli
network-slave-2.psg.network ansible_host=192.168.49.57 ansible_user=moeen.tavakoli
```

