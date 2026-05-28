# ansible-server-bootstrap

An Ansible playbook for quickly bootstrapping my servers.

## What it does:

1. Installs the base packages.

2. Installs and configures firewalld.

3. Enables automatic security patch updates.

4. Configures notifications to be sent to Pushover if a server restart is required after an update.

5. Apply dev-sec os and ssh hardening.

6. Installs and configures CrowdSec with nftables firewall bouncer.

7. And adds a couple of additions depending on the server's role.

## hosts.yaml example

```yaml
all:
  vars:
    pushover_user_key: "exampleusertoken"
  
  children:
    homelab:
      hosts:
        example.com:
          enable_ssh_password: true
      vars:
        pushover_app_token: "rqwrwqeqweqeqe"
    vps:
      hosts:
        example1.com:
      vars:
        pushover_app_token: "examplewewewewe"
```
