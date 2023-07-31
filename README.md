# Ansible management of hetzner servers

## Setup

Basic ansible setup:

```bash
python3 -m pip install --user pipx
python3 -m pipx ensurepath
pipx install --include-deps ansible
# for autocompletions
# pipx inject PACKAGE DEPENDENCIES
# will install a python module into the pipx managed package (venv)
pipx inject ansible argcomplete 
# The Hetzner Cloud dynamic inventory plugin requires python-dateutil and requests .... APPARENTLY
pipx inject ansible requests
pipx inject ansible python-dateutil
```

Ansible HCloud specific setup: 

```bash
ansible-galaxy collection list | grep hetzner.hcloud # should be version 1.x.x
```
