# db8-joomlabox
A virtual environment with LAMP Stack for Joomla using Virtualbox + Vagrant + Ansible to set up and deploy it.


## LAMP Stack
This deployment tool will create a virtual environment with LAMP stack for older Joomla versions

* Debian 8 (Jessie) Linux: Official Vagrant box https://app.vagrantup.com/debian/boxes/jessie64
* Apache
* MySQL (MariaDB)
* PHP 5.6
* PHPMyAdmin
* Joomla Akeeba Kickstart script 

## Requirements
* VirtualBox 5.1 and higher
* Vagrant 2.0 and higher
* Ansible 2.0 and higher


## Installation

### Install VirtualBox


### Install Vagrant


### Install Ansible


### Clone repocitory
 $ git clone https://github.com/pe7er/db8-joomlabox

### Run vagrant
 $ vagrant up

### Redo deployment
 $ vagrant provision

### Login into virtual environment
 $ vagrant ssh
 User: vagrant
 Password: vagrant

### Website accessible via
 192.168.33.100