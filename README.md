# parcels-jupyter-notebook-docker
parcels 2.0.0beta2 in jupyter base-notebook setup

The image is set up to run a jupyter base-notebook server with [parcels](http://oceanparcels.org/). I am not part of the developer team - I just combined these things into an image.

To start the parcels jupyter notebook server:
```bash
docker run -p 8888:8888 --rm -v $(pwd):/in/ -w /in/ parcels
```

Upon startup, the container will tell you which URL to paste into your browser to access the notebook, e.g.:
```bash
http://127.0.0.1:8888/?token=43be2a08031ebd897eb33d6837d8e3fa9d8614a8d11ade6
```

When running in docker-machine on Mac or Windows, you need to replace the ip address with the ip of the virtual machine.

Find the ip address of the docker-machine default virtual machine (if this is what you are using - try `docker-machine ls` to see):
```bash
docker-machine ip default
```

In my case this gives: `192.168.99.100`.

Now, paste into your webbrowser:
```bash
http://192.168.99.100:8888/?token=43be2a08031ebd897eb33d6837d8e3fa9d8614a8d11ade6
```
