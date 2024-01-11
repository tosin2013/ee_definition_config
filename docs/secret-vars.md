# Ansible Automation Platform Secret Variables

## Overview

This YAML file contains [secret-vars.yml](../secret-vars.yml) variables used by the Ansible Automation Platform playbook for authentication and configuration purposes. 

Keeping this file secure is critical to protect credentials and prevent unauthorized access.

## Details

**ee_builder_project_url_var**
- URL to the EE builder GitHub project 

**ee_registry_dest_var**
- Destination registry for pushing built EE images

**ee_registry_username_var**
- Username for accessing EE image registry

**ee_registry_password_var** 
- Password for accessing EE image registry 

**ee_validate_certs_var**
- Whether to validate certificates for registry connections

**base_registery_username_var** 
- Username for accessing base image registries

**base_registery_password_var**
- Password for accessing base image registries  

**ah_host_var**
- Hostname of the Automation Platform controller

**ah_token_var**
- Token for accessing Automation Platform API

**controller_hostname_var** 
- URL of the Automation Platform controller

**controller_username_var**
- Admin username for Automation Platform access

**controller_password_var**  
- Admin password for Automation Platform access  

**controller_validate_certs_var**
- Whether to validate controller certificates 

**remote_builder_hostname_var**
- IP address of remote build server

**remote_builder_username_var** 
- Username for accessing remote build server over SSH

**remote_builder_password_var**  
- Password for accessing remote build server over SSH

**default_base_image_var** 
- Default base image to use for building EEs

**username_var**
- Variable used by test playbook survey

This covers the main sensitive variables that should be protected. Restricting access through permissions, encryption, secrects management, etc. is highly recommended.