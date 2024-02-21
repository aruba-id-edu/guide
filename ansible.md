# What is Ansible

## Ansible automates the management of remote systems and controls their desired state.
![image](https://github.com/aruba-id-edu/guide/assets/137608707/3f01d61c-4a9a-4caa-b2a3-8ef3c8139eea)

As shown in the preceding figure, most Ansible environments have three main components:

### Control node
A system on which Ansible is installed. You run Ansible commands such as ansible or ansible-inventory on a control node.

### Inventory
A list of managed nodes that are logically organized. You create an inventory on the control node to describe host deployments to Ansible.

### Managed node
A remote system, or host, that Ansible controls.

## Ansible provides open-source automation that reduces complexity and runs everywhere.

As automation technology, Ansible is designed around the following principles:

### Agent-less architecture
Low maintenance overhead by avoiding the installation of additional software across IT infrastructure.

### Simplicity
Automation playbooks use straightforward YAML syntax for code that reads like documentation. Ansible is also decentralized, using SSH existing OS credentials to access to remote machines.

### Scalability and flexibility
Easily and quickly scale the systems you automate through a modular design that supports a large range of operating systems, cloud platforms, and network devices.

### Idempotence and predictability
When the system is in the state your playbook describes Ansible does not change anything, even if the playbook runs multiple times.

# What's Next

Install Ansible and OS-CX Collection

FYI: 

https://www.ansible.com/integrations/networks/aruba

https://github.com/aruba/aoscx-ansible-collection

https://github.com/aruba/aoscx-ansible-workflows

## Install Ansible

Ansible Prerequisites:

Python 3.5 or later

Install Guide: https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#installation-guide

## Install OS-CX Collection

OS-CX Collection Prerequisites:

Python 3.5 or later

Ansible 2.9.0 or later

Minimum supported AOS-CX firmware version 10.04

Enable REST on your AOS-CX device with the following commands:

```
switch(config)# https-server rest access-mode read-write
switch(config)# https-server vrf mgmt
```

Install Guide: https://developer.arubanetworks.com/aruba-aoscx/docs/getting-started-with-ansible-and-aos-cx

# Ansible and OS-CX

FYI:

https://github.com/aruba-id-edu/ansible-aruba-sw-cx

## Backup Config

```
---
- name: backup config aruba switch cx
  hosts: switch-lab
  collections:
    - arubanetworks.aoscx

  vars:
    ansible_connection: network_cli
    ansible_network_os: arubanetworks.aoscx.aoscx
    #ansible_username: 
    #ansible_password:

  tasks:  
  - name: running show running-config
    aoscx_command:
      commands:
        - show run
    register: output

  - name: save file
    copy:
      content: "{{ output.stdout | join('\n') }}"
      dest: "./{{ inventory_hostname }}.cfg"
```

## Change VLAN

```
---
- name: add vlan aruba switch cx
  hosts: switch-lab
  collections:
    - arubanetworks.aoscx

  vars:
    ansible_connection: network_cli
    ansible_network_os: arubanetworks.aoscx.aoscx
    #ansible_user:
    #ansible_password:

  tasks:
  - name: create vlan
    aoscx_command:
      commands:
        - configure terminal
        - vlan {{new_vlans}}
        - end
  - name: trunk port
    aoscx_command:
      commands:
        - configure terminal
        - interface {{item}}
        - no routing
        - vlan trunk allowed {{trunk}}
        - vlan trunk native {{native}}
        - end
    loop: "{{trunk_port}}" 
  - name: access port
    aoscx_command:
      commands:
        - configure terminal
        - interface {{item}}
        - no routing
        - vlan access {{access}}
        - end
    loop: "{{access_port}}"
  - name: save configuration
    aoscx_command:
      commands:
        - write mem
```
