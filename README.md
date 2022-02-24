# Ansible Developer Demo

## Demo Scenarios

1. Create Custom Collection
2. Create Custom EE with collection from point 1
3. Upload Custom EE to On-Prem Automation Hub
4. Use Custom Collection with ansible-navigator
5. Use Custom Collection with Controller

### Create Custom Content Collection

#### Collection Skeleton

`ansible-galaxy collection init --init-path ./ jacek.custom_app`

#### Place Content

Place Roles, modules, plugins etc.

In my case I will copy previously prepared roles and copy modules from ansible.posix collection

#### Build collection

In collection dir start following:

```bash
ansible-galaxy collection build
```
