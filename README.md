## ansible

Ansible is tools that can help us to automate IT tasks 

We have 2 type of servers : 

1. control machin 
2. nodes


When we want to use ansible there are some step to do it 

let`s do it 

##  step 1

Install ansible and dependeny in control machine


```
sudo apt-get update
sudo apt-get install software-properties-common
sudo apt-add-repository ppa:ansible/ansible
sudo apt-get update
sudo apt-get install ansible
```
##  step 2

Install openssh on nodes

```bash
sudo apt-get install openssh-server
sudo systemctl enable ssh
sudo systemctl start ssh # start ssh
sudo systemctl status ssh # check status
```

##  step 3

Create keys (public and private key) in control machine 

`ssh-keygen -t rsa`

it create two key 

1-private key --> id_rsa

2- public key --> id_rsa.pub


Default directory for save ssh-key is `~/.ssh` so we create this directory .

```
ssh USERNAME@IP-OR-HOSTNMAE
mkdir -p .ssh
```

We want to make secure connection on control machine and nodes so send public key of the control machine to all nodes 

`ssh-copy-id -i id_rsa.pub USERNAME@IP-OR-HOSTNMAE`

Now we have secure connection between control machine and nodes 


## define groups in ansible



Add some groups in make easier for us to manage and  grouping all nodes
groups define in `/etc/ansible/hosts` and there are lots of defualt groups that is comment.
if we want to add groups must be edit this file and add groups like commented groups 

There are many syntax to define nodes 

Popular syntax is \
`HOSTNAME ansible_host=IP ansible_user=USERNAME `

```
[network]

network-master-1.psg.network ansible_host=192.168.50.1 ansible_user=moeen.tavakoli
network-slave-2.psg.network ansible_host=192.168.49.57 ansible_user=moeen.tavakoli
```

To check add groups and nodes use this command to see all nodes that you added 

`ansible --list-hosts all`

This command pring list of groups and hosts that you added into groups  


## Check connection

There many ways to check connection but easy way to check connection is use `ping` option 

`ansible -m ping all`


This command send request to check status of connection.

This command return  obejct that send  response to see all connection status and some message 
the most property of response is status that we want to recive `SUCCESS`


### execute commands in nodes
When we have secure connection on control machine and nodes , we can excute command from control machine and excute on nodes then see all changes on control machine
so we push commands from control machine and expect to execute on nodes (group or all) then return changes and see all response in control machine 

We can use this command to send command that called `modules`

`ansible all-or-groupName -a "COMMANDS"`

For example

`ansible Network -a "echo $HOSTNAME"`

This command retrun have 4 step 

### step 1
Send this script (`echo $HOSTNAME`) into all nodes that memeber of `Network` group 

### step 2 
Excute script (`echo $HOSTNAME`)

### step 3 
Return changes or print data that returns from nodes into control machine 

### step 4 
Control machine recive data and print number of changes

[ansible toturial on yt](https://www.youtube.com/watch?v=5hycyr-8EKs)


[official ansible doc](https://docs.ansible.com/)

