# ee_definition_config
Use the EE builder using configuration Job in Controller

[Blog post discussing how to use this repo](https://www.redhat.com/architect/ansible-execution-environment-automated-build)

## Requirements install collections
```bash
ansible-galaxy collection install  -r collections/requirements.yml 
```


## Files and purposes

### Configure Controller
Configure controller to create all controller objects to create a Job template that can create an EE. 
Changes will need to made to credentials and the inventory to be applicable to your installation.
```bash
ansible-playbook  configure_controller.yaml  -e "@secret-vars.yml"  -vvv
```

### Configure Controller for Microshift Deployments on AWS
```bash
ansible-playbook  microshift-ansible-aws-roles.yaml  -e "@secret-vars-microshift-ansible-aws-roles.yml" -e "@projects/ansible-aws-roles/microshift-ansible-aws-vars.yaml"  -vvv
```

#### No Survey
```bash
ansible-playbook -i inventory configure_controller_no_survey.yaml  -e "@secret-vars.yml"  -vvv
```

### Load Execution Environment
```bash
ansible-playbook  push_to_controller.yaml  -e "@secret-vars.yml"  -vvv
```
### Load Execution Environment for Microshift Deployments on AWS
```bash
export USERNAME=takinosh
export TAG=testing
ansible-playbook push_to_controller.yaml -e "ee_name_var=ansible-aws-roles" -e "set_ee_registry_dest_var=quay.io/${USERNAME}/ansible-aws-roles:${TAG}"  -e "@secret-vars-microshift-ansible-aws-roles.yml"
```


### EE Builder Survey
The playbook used in the controller Job template to create an EE.

### Survey Inputs
File to copy survey inputs from to get examples of format.

### EE builder base
Base EE definition file to create an EE with a playbook.

### EE Venv migrate
Playbook that when pointed at a Tower will create Execution environments based on the Towers defined Venvs.

### EE Builder local survey
Test file for testing survey options

## See Docs for more information
* [Ansible Automation Platform Configuration](docs/configure-controller.md)
* [Ansible Automation Platform Secret Variables](docs/secret-vars.md)