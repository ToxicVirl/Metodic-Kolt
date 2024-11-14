      git clone https://github.com/skl256/grafana_stack_for_docker.git

.

      cd grafana_stack_for_docker

.  

      sudo mkdir -p /mnt/common_volume/swarm/grafana/config 
.

      sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data,loki-data,promtail-data} 
.

      sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana} 
.
    
      touch /mnt/common_volume/grafana/grafana-config/grafana.ini 

.

      cp config/* /mnt/common_volume/swarm/grafana/config/

.

      mv grafana.yaml docker-compose.yaml 

.

      sudo yum install curl

.

      COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d" -f4)

.

      sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose

.

      sudo chmod +x /usr/bin/docker-compose

.

      sudo chmod +x /usr/bin/docker-compose

.

      sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo

.

      sudo yum install docker-ce docker-ce

.

      sudo systemctl enable docker --now

.

      docker compose up -d


      


      






      
