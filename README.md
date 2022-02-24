# Ansible Developer Demo

## Demo Scenarios

1. Create Custom Collection
2. Create Custom EE with collection from point 1
3. Upload Custom EE to On-Prem Automation Hub
4. Use Custom Collection with ansible-navigator
5. Use Custom Collection with Controller

### 1. Create Custom Content Collection

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

### Publish collection (Automation Hub On-Prem)

1. Create namespace on Hub
2. Upload collection archive

## 2. Create Custom EE with custom_app collection

### Login to registry

```bash
podman login registry.redhat.io
```

### Create all required files for custom_app_ee

#### requirements.yml

```yaml
---
collections:
  - jacek.custom_app

```

#### ansible.cfg

```ini
[galaxy]
server_list = published_repo

[galaxy_server.published_repo]
url=https://jskauthub.redhat.lab/api/galaxy/content/published/
token=
```
