# Docker + RDkit + Conda + Jupyter

1. Install [docker]('https://www.docker.com/community-edition') for mac.
2. clone this repo: 
3. Build the docker image from the Dockerfile (in current directory)

    docker build -t run_rdkit_conda .

4. Run the docker container:
    
    docker run -d -p 8888:8888 -t run_rdkit_conda /bin/bash -c "jupyter notebook --notebook-dir=/tmp --ip=* --allow-root"

5. Docker will return a container ID, type `docker log <id>`. Note: you do not have to type the entire ID, just the first three letters/numbers

6. You should see a log printed to STDOUT from Jupyter, providing a URL to access the notebook. Copy this URL and paste into your browser. 

7. The URL might look like this __________, replace ________, with ____________. 
