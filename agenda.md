# Docker Presentation Agenda:

## Part 1: enter the sandbox

1. `docker pull ubuntu:xenial` from [DockerHub](https://hub.docker.com/_/ubuntu/)
2. `docker run`
3. test in ubuntu environment, run `apt-get update`
4. 

## Part 2: real fun begins

1. `git clone` [this repo](https://github.com/simonkeng/rdkit-jupyter-docker)
2. follow instructions in README.md
3. `docker cp` the files from git repo and add them to `/my_data` in container. Full command `docker cp example.sdf <container>:/my_data/test.sdf`
