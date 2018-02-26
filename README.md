# Ansible Target

Docker image used for testing Ansible playbooks from an [ansible_playbook](https://github.com/philm/ansible_playbook) Docker container.

Essentially this is a test-friendly SSH server with an "Ubuntu:16.04" user and other optimizations.

Example Usage:
```
docker network create -d bridge --subnet 172.25.0.0/16 isolated_nw

docker run -d -p 2222:22 \
  --name ansible_target \
  --network=isolated_nw \
  -v ~/.ssh/id_rsa.pub:/home/ubuntu/.ssh/authorized_keys \
  localhost:5000/ansible_target:latest
```
