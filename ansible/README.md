# Ansible notes

Short, practical notes collected while studying and testing.

## Run ad-hoc ping

```bash
ansible all -i inventory.ini -m ping
```

## Check mode with diff

```bash
ansible-playbook site.yml --check --diff
```
