# RDKit + Chem + Conda + Jupyter + Docker

Easily run a Jupyter notebook in Python 3, with all the RDKit dependencies and packages baked in. I hope this provides an "out of the box" solution for anyone who would like to replicate  [this](http://asteeves.github.io/blog/2015/01/12/molecules-in-rdkit/) or [this](https://github.com/rdkit/UGM_2016/blob/master/Notebooks/Brief%20Introduction.ipynb), but does not want to spend hours installing packages, dealing with virtualenvs, conda envs, dependencies, and getting all the right pieces talking for RDKit and Jupyter to live happily together (in my experience, this is _not_ trivial).

1. Install [Docker](https://www.docker.com/community-edition).
2. Clone this repo: `git clone https://github.com/simonkeng/rdkit-jupyter-docker.git`
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

7. The URL might look like this: `http://11140d529dec:8888/?token=6ae1624a03f82e5592feaa5123b4086a5dc4f54ed6f6fe8b`, replace the part right after `http://` (in this URL example: `11140d529dec`), with `127.0.0.1`. So the final URL should look like `http://127.0.0.1:8888/?token=6ae1624a03f82e5592feaa5123b4086a5dc4f54ed6f6fe8b` (except with your token). _Note:_ this is currently a Jupyter bug, its very likely that this step won't be necessary by the time you run this container.

### Caveats
If you are running any other processes on port 8888 (e.g. another Jupyter notebook) then you will likely have problems connecting to the notebook in the browser. I recommend shutting down any other Jupyter notebooks first, before running `docker run` command.

## Acknowledgement

This implementation was forked from Greg Landrum's [rdkit containers](https://github.com/rdkit/rdkit_containers/tree/master/docker/run_conda3) repo, but I've tweaked it a bit and updated the things that didn't work for me initially, in hopes to provide an "out of the box" build, relevant to May 2018 developers. All credit goes to Greg and the other RDKit devs.
