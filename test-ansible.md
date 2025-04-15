# Inventories

#1.inventories are how ansible can locate and run against multiple systems
#
#2.you can think inventory as a list of hosts
#
#3.By-default Ansible uses /etc/ansible/hosts as its inventory  but this is configurable
#
#4.Inventories may be formatted as an INI file or as a yml file

#***********************EXAMPLE ANSIBLE FILE*************************

all:                          #top level group with all hosts and child group
  hosts:                      #comes under "all" group this section lists individual hosts and isn't part of any subgroups
    mail.example.com
  children:                   #new section where you define groups inside the all group.
    webservers:               #CUstom group name that holds specific hosts
      hosts:
        junior.example.com    #hosts
        gun.example.com       #hosts
    observers:
      hosts:
        db[1:4].example.com


#***************************MODULES**********************************

#Modules are essential tools for particular tasks

#they take parameters and return json

#can run in cmd line or within playbook

#custom modules can be written


#***************************VARIABLES********************************

#similar to javascript

#scoping works


#***************************FAcTS************************************

#provides certain information about given target host

#Facts are discovered by Ansible automatically when it reaches out to a host


#***************************PLAYS & PLAYBOOKS************************

#The goal of the play is to map a group of hosts to well-defined roles

#A play may use one or more modules to achieve desired end state

#A playbook is a series of plays

#a play book can deploy new webserver , install new application to existing application server, run sql against some database servers to support new application


#***************************CONFIGURATION FILES***********************

#possible locations
#  - ANSIBLE_CONFIG (an environment variable)
#  - ansible.cfg (in the current directory)
#  - .ansible.cfg (in the home directory)
#  - /etc/ansible/ansible.cfg (master configuration)

#Configuration can also be set in environment variables

#Some commonly used settings:
  - ansible_managed
  - forks
  - Inventory


#***************************Ad-hoc***********************
#similar to bash command
#-m says module 
  #-so -m file -> file module
#quick note we need to append the file before change to another group or else it will wipe out previous group


#***************************Inventory Management***********************
#An inventory is a list of hosts that Ansible manages

#***************************Block Groups***********************
#Block groups and rescues - like a try and catch.

#***************************Selectively Run Specific Tasks In Playbooks Using Tags***********************
#tags we can deploy only application stage or only database stage







































