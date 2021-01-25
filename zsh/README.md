# The information for zsh + oh my zsh + powerlevel10k

For the current version is just compatible with Linuxmint 19.3 Tricia

## Requirement

- Ansible 2.9.6
- Python: 2.7.17


## Source

**Oh my zsh**: https://github.com/ohmyzsh/ohmyzsh

**powerlevel10k**: https://github.com/romkatv/powerlevel10k/blob/master/README.md

## Execute

```bash
    ansible-playbook playbooks/install-oh-my-zsh.yml -i inv.ini 
```

## Config

### **Fix vs code font**

1. Go to `File -> Preferences -> Settings`

1. Find and select `Edit in settings.json`

1. Add these two line to the setting file

```json
    "terminal.integrated.shell.linux": "/usr/bin/zsh",
    "terminal.integrated.fontFamily": "'MesloLGS NF'"
```

### **P10K Config**

```bash
    ❯ p10k
    Usage: p10k command [options]

    Commands:

    configure  run interactive configuration wizard
    reload     reload configuration
    segment    print a user-defined prompt segment
    display    show, hide or toggle prompt parts
    help       print this help message

    Print help for a specific command:

    p10k help command
```
