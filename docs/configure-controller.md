# Ansible Automation Platform Configuration
![20240111111008](https://i.imgur.com/Pr2r1F5.png)

## Overview
- [configure_controller.yaml](../configure_controller.yaml) playbook is used to configure Ansible Automation Platform by using the Ansible controller configuration modules. It will create inventories, projects, credentials, hosts, and job templates.

## Prerequisites
- Ansible Automation Platform installed 
- Control node with Ansible installed and tower-cli configured for access
- Variables defined for Automation Platform credentials and systems to manage

## Details

1. Gather Facts set to false since this is configuring the Automation Platform API not managing hosts
2. Imports variables from external files using Jinja2 templates
3. Defines credentials used to access Automation Platform API 

4. Creates 2 inventories:  
    - Controller Hosts: For local control node
    - Remote Build Servers: For remote hosts

5. Creates hosts in the inventories: 
    - localhost: For running jobs on the control node  
    - remote_builder_hostname: For running jobs on the remote build server

6. Creates a credential type for storing registry credentials

7. Creates credentials using the registry credential type to securely store passwords/tokens  

8. Creates an Ansible project for checking out playbooks from SCM

9. Creates a job template for building execution environments: 
    - Uses the Remote Build Servers inventory 
    - Credential to access registries 
    - EE Builder project
    - Builder playbook with survey for image customization 
    - Survey enabled for user input when launching job

10. Creates a job template for testing built execution environment:
    - Uses local Controller Hosts inventory
    - EE Builder project
    - Test playbook
    - Survey enabled for user input  
    - Custom execution environment variable specified   

11. Roles used to configure Automation Platform objects using controller configuration modules

The playbook automates setup of infrastructure on Ansible Automation Platform to implement CI/CD pipelines for building and testing execution environments. Surveys allow customization of the jobs when launched. Extra variables pass data at run time.

# Screen Shots of after running Execution Environment Builder job template:
![20240111111126](https://i.imgur.com/RV3OfLT.png)