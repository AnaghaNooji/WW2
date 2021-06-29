## Ansible Configuration

### Prerequisites
#### Ansible Version and Installation:
Command **_ansible --version_** gives the info of the ansible version 

Recent Ansible version used in storage environment is **2.9.6** and python version **3.7.5**

One can install a released version of Ansible with pip or a package manager. Refer [installation guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html "Installing Ansible") for details on installing Ansible.

### Steps to configure and run playbook

#### Git Configuration
##### Git clone your fork repo
On GitHub, navigate to your fork, click Clone or download. Choose 'Use SSH' and copy the clone URL for the repo.

On your Linux system, under your work directory:

>git clone https://github.dxc.com/DXC-Storage-Automation/docs.git
Then, cd to your cloned repo, show the list of created remotes:

ansible-project
>git remote -v

origin https://github.dxc.com/DXC-Storage-Automation/docs.git (fetch)

origin https://github.dxc.com/DXC-Storage-Automation/docs.git (push)

When a repo is cloned, it has a default remote called origin that points to your fork on GitHub.



#### inventory.ini
INI file based inventory, sections are groups or group related with special :modifiers.
It can be either a single file or script or a directory containing static inventory files or scripts. This inventory is automatically loaded and provided to Ansible when invoked and can be further overridden on the command line or via the ANSIBLE_INVENTORY environment variable to specify the hosts directly. _(Giving an absolute path for the inventory location is best practice, because relative paths are interpreted relative to the current working directory which defaults to the project directory)_

For more info on inventory.ini file refer [Ansible INI File](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/ini_inventory.html) 

#### ansible.cfg
With a fresh installation of Ansible, like every other software, it ships with a default configuration file.The file governs the behavior of all interactions performed by the control node. In Ansible’s case that default configuration file is (ansible.cfg) located in /etc/ansible/ansible.cfg. This is the [Ansible Configuration File](https://docs.ansible.com/ansible/latest/installation_guide/intro_configuration.html#configuration-file) 

#### Run playbook
Inventory file tells ansible to consider the host name as an inventory
>pwd

Locate yourself to the present working directory and run the following command
>ansible-playbook _you_playbook_.yml -i inventory/hosts_dxc

When you run this playbook it would be run against all the host groups specified in your inventory file.

_To have an interactive prompt one can add the --ask-vault-pass to any ansible or ansible-playbook command. Ansible will prompt you for a password which it will use to try to decrypt any vault-protected content it finds._



