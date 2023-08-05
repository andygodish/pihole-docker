# Pi-hole

- [Image Tags](https://hub.docker.com/r/pihole/pihole/tags)

Notes for running pi-hole for as a local DNS server on your LAN. In this repo is a docker-compose.yaml used to deploy the application. 

## Ports

- 53    TCP/UDP     DNS 
- 80    TCP         HTTP

## Gravity Sync

- [Github Repo](https://github.com/vmstan/gravity-sync/wiki/System-Requirements)

This tools allows you to automatically sync two pi-hole instances. 

> Passwordless sudo on both serve

Follow the initialization process by running the following script:

```
curl -sSL https://raw.githubusercontent.com/vmstan/gs-install/main/gs-install.sh | bash

```

In my situation, I was only able to configure `gravity-sync` on my first pihole instance (primary), the second one errored out indicating a permission error in the /tmp directory. I was able to perform a `gravity-sync push` command and see my local DNS settings replicated in my secondary pihole instance. After this, I ran `gravity-sync auto` and I was able to demonstrate that my configurations were being pushed automatically on a regular basis. 
