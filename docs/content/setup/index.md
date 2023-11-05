---
title: Setup
weight: 1
---

# Prerequisites

These playbooks assume certain minimum requirements:

  1. Python
  2. Ansible
  3. Git
  4. A non-root user, `os_user=ansible-runner`, which belongs to `os_group=ansible-runners` and is permitted to `sudo`

## User Data

The following user data may be added to the Droplet/VM initialization process:

```
apt-get update
apt-get install -y software-properties-common
add-apt-repository --yes --update ppa:ansible/ansible
apt-get install -y ansible
groupadd ansible-runners
useradd -m -g ansible-runners ansible-runner
echo "ansible-runner ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/ansible-runner
chmod 0440 /etc/sudoers.d/ansible-runner
```
