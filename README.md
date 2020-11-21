# IP-3-Configuration-Management

Requirements
Make sure that you have the following installed:
- Ansible 2.10.3 
- Git
- Vagrant
- Virtual Box
- Hypervisor functionality on the host machine enabled on BIOS
- CentOS 7 - The Solution has only been tested on CentOS 7 as Host

## Clone the repository to the guest
- [Clone the repositoty] (https://github.com/popiyo/IP-3-Configuration-Management.git)
- https://github.com/popiyo/IP-3-Configuration-Management.git

## Provision the solution
- On the root folder (location of Vagrantfile) of the cloned repo  run 
 `vagrant up`
- the installation can take upto 30 minutes depending on your internet connection

## Accessing the deployed solution
- the solution will ONLY work when accessed from witin the Guest Machine
- This is because the architecture of the ecommerce server API points explicitly to an static IP: 192.168.60.10
- On a browser, access the app on 192.168.60.10

## ISSUE: Data Persistence

- The Installation could not allow Mongo on the VM to write to the shared folder of Guest
- I was not able to figure out how to configure write access from mongodb user to the shared folder owned by vagrant user.
- This also failed despite testing by adding vagrant user to the mongodb user group. Mongo would fail to lauch whenever the data directory was on the VM shared folder.


