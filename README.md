# Ansible NGINX Role (open source)

> This role custom from official release [Ansible NGINX [here](https://github.com/nginxinc/ansible-role-nginx-config).]

This role installs NGINX Open Source, or the NGINX Amplify agent on your target host.

## Requirements

### Ansible

- This role is developed and tested with [maintained](https://docs.ansible.com/ansible/devel/reference_appendices/release_and_maintenance.html) versions of Ansible core (above `2.12`).
- When using Ansible core, you will also need to install the following collections:

    ```yaml
    ---
    collections:
      - name: ansible.posix
        version: 1.5.4
      - name: community.general
        version: 6.4.0
      - name: community.crypto # Only required if you plan to install NGINX Plus
        version: 2.14.1
      - name: community.docker # Only required if you plan to use Molecule (see below)
        version: 3.4.7
    ```
    **Note:** You can alternatively install the Ansible community distribution (what is known as the "old" Ansible) if you don't want to manage individual collections.
- You will need to run this role as a root user using Ansible's `become` parameter. Make sure you have set up the appropriate permissions on your target hosts.
- Instructions on how to install Ansible can be found in the [Ansible website](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#upgrading-ansible-from-version-2-9-and-older-to-version-2-10-or-later).

### Jinja2

- This role uses Jinja2 templates. Ansible core installs Jinja2 by default, but depending on your install and/or upgrade path, you might be running an outdated version of Jinja2. The minimum version of Jinja2 required for the role to properly function is `3.1`.
- Instructions on how to install Jinja2 can be found in the [Jinja2 website](https://jinja.palletsprojects.com/en/3.1.x/intro/#installation).

## Installation

### Ansible Galaxy

### Git

To pull the latest edge commit of the role from GitHub, use:

```bash
git clone https://github.com/nginxinc/ansible-role-nginx.git
```

## Platforms

The NGINX Ansible role supports all platforms supported by [NGINX Open Source](https://nginx.org/en/linux_packages.html), [NGINX Plus](https://docs.nginx.com/nginx/technical-specs/), and the [NGINX Amplify agent](https://github.com/nginxinc/nginx-amplify-doc/blob/master/amplify-faq.md#21-what-operating-systems-are-supported):

### NGINX Open Source

```yaml
AlmaLinux:
  - 8
  - 9
Alpine:
  - 3.15
  - 3.16
  - 3.17
  - 3.18
Amazon Linux:
  - 2
CentOS:
  - 7.4+
Debian:
  - bullseye (11)
  - bookworm (12)
Oracle Linux:
  - 7
  - 8
  - 9
Red Hat:
  - 7.4+
  - 8
  - 9
Rocky Linux:
  - 8
  - 9
SUSE/SLES:
  - 12
  - 15
Ubuntu:
  - focal (20.04)
  - jammy (22.04)
  - kinetic (22.10)
  - lunar (23.04)
```

### NGINX Amplify Agent

```yaml
Amazon Linux 2:
  - any
Debian:
  - buster (10)
  - bullseye (11)
Red Hat:
  - 8
Ubuntu:
  - bionic
  - focal
```

**Note:** You can also use this role to compile NGINX Open Source from source, install NGINX Open Source on compatible yet unsupported platforms, or install NGINX Open Source on BSD systems at your own risk.

## Role Variables

This role has multiple variables. The descriptions and defaults for all these variables can be found in the **[`defaults/main/`](https://github.com/nginxinc/ansible-role-nginx/blob/main/defaults/main/)** folder in the following files:

| Name | Description |
| ---- | ----------- |
| **[`main.yml`](https://github.com/nginxinc/ansible-role-nginx/blob/main/defaults/main/main.yml)** | NGINX installation variables |
| **[`amplify.yml`](https://github.com/nginxinc/ansible-role-nginx/blob/main/defaults/main/amplify.yml)** | NGINX Amplify agent installation variables |
| **[`bsd.yml`](https://github.com/nginxinc/ansible-role-nginx/blob/main/defaults/main/bsd.yml)** | BSD installation variables |
| **[`logrotate.yml`](https://github.com/nginxinc/ansible-role-nginx/blob/main/defaults/main/logrotate.yml)** | Logrotate configuration variables |
| **[`selinux.yml`](https://github.com/nginxinc/ansible-role-nginx/blob/main/defaults/main/selinux.yml)** | SELinux configuration variables |
| **[`systemd.yml`](https://github.com/nginxinc/ansible-role-nginx/blob/main/defaults/main/systemd.yml)** | Systemd configuration variables |
| **[`directory.yml`](https://github.com/nginxinc/ansible-role-nginx/blob/main/defaults/main/directory.yml)** | NGINX information directory configuration variables |
| **[`modify.yml`](https://github.com/nginxinc/ansible-role-nginx/blob/main/defaults/main/modify.yml)** | Modify systemd configuration variables |

## License

Apache License, Version 2.0

## Author Information

This Ansible role was created in 2023 by [Asapdotid](https://github.com/asapdotid).
