# Minecraft Ansible

Ansible configuration for a Minecraft server

Stealing everything from here: https://github.com/chadgeary/minecraft

# Setup

## Install Ansible & Git

```sh
sudo apt update && sudo apt install -y ansible git
```

## Deploy

```sh
git clone https://github.com/petitJAM/minecraft-ansible && cd minecraft-ansible

ansible-playbook minecraft.yml --extra-vars "target=localhost"
```

# Maintenance

Update and restart service:
```
ansible-playbook minecraft.yml --extra-vars "target=localhost mc_update=True"
```
