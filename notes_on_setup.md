## Docker start 

If the docker service is not yet started, run
```bash
sudo systemctl start docker
```

## Probe setup

The permissions on the pico probe need to be set right to enable the container to access the probe. For this reason, copy the ```68-pico-probe.rules``` file to ```/etc/udev/rules.d/``` on the **local** machine and run

```bash
sudo udevadm control --reload && sudo udeadm trigger
```
to make sure the rules are enforced. The container might need a restart to see the probe, on your **local** machine run ```docker ps``` to list docker containers running and run ```docker restart <container_name>``` to restart it.