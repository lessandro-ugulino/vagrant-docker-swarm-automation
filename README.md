# Vagrant Docker Swarm Automation

This pipeline is based on this [documentation](https://medium.com/@lessandro.ugulino/docker-swarm-part-5-d7ccccb98ff8). It will deploy six docker swarm services on [VirtualBox](https://www.virtualbox.org/) via [Vagrant](https://www.vagrantup.com/).

## Index

- [Requirements](#req)
- [Architecture](#Architecture)
- [How to Deploy](#howto)
- [Optional: Access Vagrant Virtual Machine](#Optional)
- [Result](#Result)
- [Delete the env](#Delete)

<a name="req"></a>

## Requirements

These tools need to be installed on your local machine or the computer that will run Ansible:

- <a href="https://www.vagrantup.com/downloads">Vagrant</a>
- <a href="https://www.virtualbox.org/wiki/Mac%20OS%20X%20build%20instructions">VirtualBox</a>
- <a href="https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installing-ansible-on-macos">Ansible</a>

<a name="Architecture"></a>

## Architecture

This automation will deploy 2 docker nodes and 1 docker master as shown below.

![diagram](img/diagram.png)

_Docker application that will be deployed via this automation_

![Arch](img/docker-swarm.png)

<a name="howto"></a>

# How to Deploy

Execute on the current folder:

```
vagrant up --no-provision
```

Once the provisioning is done, run the below command

```
vagrant provision
```

<a name="Optional"></a>

## Optional: Access Vagrant Virtual Machine

You can access the VM executing the below command on the current folder

```
vagrant ssh docker-master
```

This command will `ssh` to docker-master VM.

<a name="Result"></a>

## Result

The below output is expected, and once it's done you can access `192.168.165.117` IP address on ports `5000` and `5001`

![ansible](img/ansible.png)

![broswer](img/broswer.png)

<a name="Delete"></a>

## Delete the env

```
vagrant destroy
```
