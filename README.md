# Docker + RDkit + Conda + Jupyter

1. Install [docker](https://www.docker.com/community-edition) for macOS.
2. Clone this repo to get the Dockerfile: `https://github.com/simonkeng/rdkit-jupyter-docker.git`
3. Build docker image from Dockerfile

```bash
 docker build -t run_rdkit_conda .
```

4. Run the docker container:

```bash
    docker run -d -p 8888:8888 -t run_rdkit_conda /bin/bash -c "jupyter notebook --notebook-dir=/tmp --ip=* --allow-root"
```

5. Docker will return a container ID, type `docker logs <id>` passing in the first three characters from the id.

6. This command should print a message to STDOUT, from Jupyter running in the container, providing a URL to access the notebook. Copy this URL and paste it into your browser.

7. The URL might look like this __________, replace ________, with ____________.

This workflow and implementation was heavily copied from Greg Landrum's [rdkit containers]('https://github.com/rdkit/rdkit_containers/tree/master/docker/run_conda3') resource, but tweaked and updated for 05/23/2018
