# EMQX on Raspberry Pi using Docker

Running on Pi 4, 64bit Raspbian.

Docker file has the following:

- Watchtower (Auto-update container images)
- Portainer (Docker GUI)
- EMQX (MQTT Broker)

EMQX requires some config files, its best to boot the container outside of docker-compose first and then open a shell into it and just copy out the configs.

- `/opt/emqx/etc/acl.conf`
- `/opt/emqx/etc/emqx.conf`
- `/opt/emqx/etc/vm.args (rename from vm.args.cloud)`

The docker container docs point to the config files on the GitHub repo for EMQX but the `etc/emqx.conf` is empty...

Also, if you install docker on latest 64 bit Rasbian it is highly recommended to use their test script to do so. Following the APT repo instructions did not work for me as they dont seem to have Docker Engine stable for 64 bit yet. 

```bash
curl -fsSL <https://test.docker.com> -o test-docker.sh
sudo sh test-docker.sh
```
