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
to make sure the rules are enforced. 

If the probe was connected after the container was started needs a restart to see the probe(check using ```docker -a``` on local machine). On your **local** machine, run ```docker restart <container_name>``` to restart it.

## Embassy integration

Copy the ```Cargo.toml```, the ```memory.x``` and the ```build.rs``` from the example directory and remove unneeded stuff from the ```.toml``` file. Make a main.rs file under the ```src``` directory or a differently named file in the ```src/bin``` directory (build/run with ```--bin <filename without extension>```). Copy the ```.cargo``` directory to the project directory.