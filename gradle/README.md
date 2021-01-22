# Ansible playbook for installing Gradle

Ansible Playbook for installing gradle
- We can specify the specific gradle version and the commandline prefix to use

## Usage

- To install local machine
```bash
  ansible-playbook playbooks/gradle.yml -i hosts.ini 
```

- To install in group of remote machines
```bash
  ansible-playbook playbooks/gradle.yml -i hosts.ini --extra-vars "hosts=remote"
```

- Besides we can specify the version we want to use in commandline
```bash
  ansible-playbook playbook/gradle.yml -i hosts.ini --extra-vars "gradle_version=6.2 command_prefix=gradle6"
```

