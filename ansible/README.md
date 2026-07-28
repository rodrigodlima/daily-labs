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

## List hosts matched by a pattern

```bash
ansible webservers --list-hosts
```

## Encrypt a single string

```bash
ansible-vault encrypt_string 's3cr3t' --name 'db_password'
```
