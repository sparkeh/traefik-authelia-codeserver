### Quickstart

You can choose to use the `example.com` domain. You will need to set your hosts file to the correct IP. If you have a domain, set this up and point to your VM IP.

 - Install ansible, be it `brew install ansible` or `apt install ansible` etc
 - Create a Ubuntu VM and update `inventory.yml` with the details. Ideally use ssh-keys as it's easier
 - Run `ansible-galaxy install -r requirements.yml` to install requirements
 - Run `ansible-playbook devbox.yml` if you've keys, otherwise something like `ansible-playbook devbox.yml -b -K` should do the trick
 - Sit back and watch applications install

 ###### Various options

 If you want to target a specific role:

 ```
> ansible-playbook devbox.yml --tags "traefik"
> ansible-playbook devbox.yml --tags "ansible"
```

...etc

For more granular config, change settings within `group_vars/all.yml` or `host_vars/`. Each role has its defaults which can be copied to suit.

