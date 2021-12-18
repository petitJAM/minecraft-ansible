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

# Notes

The `get_url` ansible task isn't working for some reason. It seems like the 
Minecraft download page is blocking script access? I can instead go to the page 
in a browser and copy the direct download link manually. Then run the following
on the server:
```sh
sudo curl <url> --output /opt/minecraft/server/server.jar
```

Then run the deploy command above.
