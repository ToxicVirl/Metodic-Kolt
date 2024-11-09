1

       sudo yum install wget

2 

       sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo

3

       sudo yum install docker-ce docker-ce-cli containerd.io

4

        sudo systemctl enable docker --now

5

     sudo yum install curl
6
    
    COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)

7

    sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose

8

    sudo chmod +x /usr/bin/docker-compose

10

     docker-compose --version

11

      cd grafana_stack_for_docker

12

      sudo mkdir -p /mnt/common_volume/swarm/grafana/config

13

    sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}

14

     sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}

15

    touch /mnt/common_volume/grafana/grafana-config/grafana.ini

16

     cp config/* /mnt/common_volume/swarm/grafana/config/

17

      mv grafana.yaml docker-compose.yaml 

18.

      sudo docker compose up -d

19.

      sudo vi docker-compose.yaml

20 

      sudo vi prometheus.yaml 










    

     
