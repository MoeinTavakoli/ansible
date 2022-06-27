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