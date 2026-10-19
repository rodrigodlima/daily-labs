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

## Limit run to one host

```bash
ansible-playbook site.yml --limit web01
```

## Gather facts for one host

```bash
ansible web01 -m setup -a 'filter=ansible_distribution*'
```

## Handlers

```yaml
handlers:
  - name: restart nginx
    ansible.builtin.service:
      name: nginx
      state: restarted
```

## Loop with dict

```yaml
- ansible.builtin.user:
    name: "{{ item.name }}"
    groups: "{{ item.groups }}"
  loop: "{{ users }}"
```
