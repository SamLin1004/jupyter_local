mkdir sam_local_docker

cd sam_local_docker


#create a docker-compose.yml file

version: '3'
services:
  jupyte-tutorial:
    image: jupyter/base-notebook
    container_name: jupyter.Sam
    ports:
      - "8888:8888"
    volumes:
      - ./work:/home/jovyan/work/
    command: start-notebook.sh --NotebookApp.token=''[user@localhost sam_local_docker]$

#make the mapping directory

mkdir work

#use docker compose

docker-compose up -d

#go to your brower and input your localhostIP:8888

# jupyter_local
