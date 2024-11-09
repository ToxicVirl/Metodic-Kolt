https://github.com/seviigva/Semenova/blob/main/1/docker-compose.yaml
1

       sudo yum install wget

![image](https://github.com/user-attachments/assets/dbe51482-e31b-4b0d-94c5-201f21a576be)
       

2 

       sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo

e![image](https://github.com/user-attachments/assets/876cf714-e48e-4174-b2e0-c368cc5d20e6)

3

       sudo yum install docker-ce docker-ce-cli containerd.io
       
![image](https://github.com/user-attachments/assets/1c802874-8fe5-42cb-a268-b7c9de735fa8)

4

        sudo systemctl enable docker --now

        ![image](https://github.com/user-attachments/assets/3f6f83c7-04f4-49c2-b02d-f66a3becc3b6)

5

     sudo yum install curl

     ![image](https://github.com/user-attachments/assets/cd5d6d1a-4858-4099-ac77-7e5f8571d8d1)

6
    
    COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)

![image](https://github.com/user-attachments/assets/3fe18973-b363-4679-ab9f-3c733b1e7263)

7

    sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose

    ![image](https://github.com/user-attachments/assets/451d85f6-369d-4717-a602-1b81507b6489)


8

    sudo chmod +x /usr/bin/docker-compose

9

     docker-compose --version

10

       git clone https://github.com/skl256/grafana_stack_for_docker.git

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

18 

       sudo docker compose up -d

19

       sudo vi docker-compose.yaml
       
20

sudo vi prometheus.yaml 






       

 
