# Ansible management of hetzner servers

## Setup

Basic ansible setup:

```bash
python -m pip install --user pipx
python -m pipx ensurepath
```

Reload your shell in order to have pipx on your PATH.

```bash
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

## Run a playbook

```bash
op run --env-file .env -- ansible-playbook fresh-setup.yaml
```