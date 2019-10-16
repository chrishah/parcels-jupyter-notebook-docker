# parcels-jupyter-notebook-docker
parcels 2.0.0beta2 in jupyter base-notebook setup

The image is set up to run a jupyter base-notebook server with [parcels](http://oceanparcels.org/) and is deposited on [Dockerhub](https://cloud.docker.com/repository/docker/chrishah/parcels-jupyter-notebook). I am not part of the developer team of parcels - I just combined these things into an image.

To start the parcels jupyter notebook server (if you haven't done so before this will first pull the image from Dockerhub which might take a few minutes):
```bash
docker run -p 8888:8888 --rm --net=host -v $(pwd):/in/ -w /in/ chrishah/parcels-jupyter-notebook:2.0.0beta2
```

Upon startup, the container will tell you which URL to paste into your favorite web-browser (tested with Google Chrome) to access the notebook server. The output will look something like this:
```bash
Executing the command: jupyter notebook
[I 12:19:26.415 NotebookApp] Writing notebook server cookie secret to /home/jovyan/.local/share/jupyter/runtime/notebook_cookie_secret
[I 12:19:27.377 NotebookApp] JupyterLab extension loaded from /opt/conda/lib/python3.7/site-packages/jupyterlab
[I 12:19:27.377 NotebookApp] JupyterLab application directory is /opt/conda/share/jupyter/lab
[I 12:19:27.379 NotebookApp] Serving notebooks from local directory: /in
[I 12:19:27.379 NotebookApp] The Jupyter Notebook is running at:
[I 12:19:27.379 NotebookApp] http://(chrishah-OptiPlex-7040 or 127.0.0.1):8888/?token=7b3b2c3b866a6812912687d6ca7320b937e99a608b53c5e1
[I 12:19:27.379 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 12:19:27.382 NotebookApp] 
    
    To access the notebook, open this file in a browser:
        file:///home/jovyan/.local/share/jupyter/runtime/nbserver-7-open.html
    Or copy and paste one of these URLs:
        http://(chrishah-OptiPlex-7040 or 127.0.0.1):8888/?token=7b3b2c3b866a6812912687d6ca7320b937e99a608b53c5e1
```

In my case (in Ubuntu), I'd 'surf' to here to access the notebook server:
```bash
http://127.0.0.1:8888/?token=7b3b2c3b866a6812912687d6ca7320b937e99a608b53c5e1
```



When running in __docker-machine__ on Mac or Windows, you need to replace the ip address with the ip of the virtual machine.

Find the ip address of the docker-machine default virtual machine (if this is what you are using - try `docker-machine ls` to see):
```bash
docker-machine ip default
```

In my case this gives: `192.168.99.100`.

Now, paste into your webbrowser, like so:
```bash
http://192.168.99.100:8888/?token=43be2a08031ebd897eb33d6837d8e3fa9d8614a8d11ade6
```
