# Minecraft Ansible

Ansible configuration for a Minecraft server

Stealing everything from here: https://github.com/chadgeary/minecraft

# Setup

## Install Ansible

```sh
sudo apt update && sudo apt install -y ansible
```

## Deploy

Make sure `host_vars/aws` has the correct server info and then run:

```sh
ansible-playbook -i hosts minecraft.yml
```

# Maintenance

Update and restart service:
```
ansible-playbook -i hosts minecraft.yml --extra-vars "mc_update=True"
```
