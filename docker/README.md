# Ansible playbook for Docker and Docker compose 

Ansible Playbook for installing Docker and Docker compose 

## Usage

### Install docker
- To install local machine
```bash
    ansible-playbook playbooks/docker.yml -i hosts.ini
```

- To install in group of remote machines
```bash
    ansible-playbook playbooks/docker-compose.yml -i hosts.ini --extra-vars "hosts=remote"
```

### Install docker-compose
- To install local machine
```bash
    ansible-playbook playbooks/docker-compose.yml -i hosts.ini 
```

- To install in group of remote machines
```bash
    ansible-playbook playbooks/docker-compose.yml -i hosts.ini --extra-vars "hosts=remote"
```

