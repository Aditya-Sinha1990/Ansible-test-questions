Role Name
=========
 Ansible role to configure a webserver running on port 81

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

# Command Usages:
-----------------

#To Initialize an Empty Structure of Apache webserver
-----------------------------------------------------
ansible-galaxy init apache --offline

# To check the syntax and indentation
-------------------------------------
 ansible-playbook testplaybook.yml --syntax-check

# To Run the playbook
----------------------
 ansible-playbook testplaybook.yml

#Listens to PORT:81 - Customized httpd.conf File - Giving flexibility to make customer specific changes
--------------------------------------------------------------------------------------------------------

# Requires work to configure inventory and domain assignment with public IP of the Server
------------------------------------------------------------------------------------------

License
-------

BSD

Author Information
------------------
Aditya Sinha
An optional section for the role authors to include contact information, or a website (HTML is not allowed).

