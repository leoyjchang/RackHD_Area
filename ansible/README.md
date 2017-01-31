###
$ ansible-playbook -i hosts/hosts-lxdcloud bootstrap.yml



###Script execution
```
$ ansible-playbook bootstrap.yml --ask-sudo
sudo password:
```

### RackHD example
# -i PATH, --inventory=PATH The PATH to the inventory hosts file, which defaults to /etc/ansible/hosts. 
# -c CONNECTION, --connection=CONNECTION Connection type to use. Possible options are paramiko (SSH), ssh, 
# and local. local is mostly useful for crontab or kickstarts. 
$ ansible-playbook -c local -i "local," bootstrap.yml

### Example at https://github.com/pistatium/ansible_atlantic_cloud/blob/master/README.md
# -k, --ask-pass Prompt for the SSH password instead of assuming key-based authentication with ssh-agent. 
ansible-playbook -i hosts/host init.yml  -vvvv -k

### Example at https://github.com/milamberspace/ansible-cloudstack-ubuntu-aio/blob/master/README.md
# -s, --sudo Force all plays to use sudo, even if not marked as such.
# -e VARS, --extra-vars=VARS Extra variables to inject into a playbook, in key=value key=value format. 
ansible-playbook -s -i ansible_hosts -e host=cs-aio1 -e user=ubuntu cs-aio-deploy.yml

### Example at https://github.com/jbinto/ansible-ubuntu-rails-server/blob/master/README.md
# -u USERNAME, --remote-user=USERNAME Use this remote user name on playbook steps that do not indicate a user name to run as. 
ansible-playbook build-server.yml -i hosts-digitalocean -u root -K -vvvv