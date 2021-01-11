## Plurasight-Ansible-GettingStarted

# Ansible's Copy Module
Format: ansible -m [module name] -a [arguments] [target server / group of target servers]
	Ex: ansible -m copy -a "src=master.gitconfig dest=~/.gitconfig" localhost

# Ansible playbook
- name: Ensure ~/.gitconfig copied from master.gitconfig
  #gather_facts: false
  hosts: localhost
  tasks: 
  - copy: src="../adhoc/master.gitconfig" dest="~/.gitconfig"

- name: Ensure homebrew packages are installed
  hosts: localhost
  tasks:
  - homebrew: name=bat state=latest
  - homebrew: 
      name: jq
      state: latest

# Ansible inventory
Path: /etc/ansible/hosts

# Ansible Console
Command: ansible-console