    sudo yum install wget

    ![image](https://github.com/user-attachments/assets/feea11b5-aa22-47fb-94c8-d9d50de1c6da)

     sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo
     
     ![image](https://github.com/user-attachments/assets/a9d9c47a-18a7-4ef9-a97b-0d4e8a4c938f)

      sudo yum install docker-ce docker-ce-cli containerd.io

      ![image](https://github.com/user-attachments/assets/7fd160d5-6097-4f01-8376-c25ee847677c)

       sudo systemctl enable docker --now

       ![image](https://github.com/user-attachments/assets/16e6e010-cfa5-4d6d-949d-fbac93ebcc5c)

        sudo yum install curl

        ![image](https://github.com/user-attachments/assets/cb2a5feb-ef08-41d8-a31b-2a66ace48cc7)

         COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)

          sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose

          ![image](https://github.com/user-attachments/assets/e670381b-a682-45ae-aec5-da9b2a4a6bc8)

           sudo chmod +x /usr/bin/docker-compose

            sudo docker-compose --version

            ![image](https://github.com/user-attachments/assets/046e7329-ccba-46e2-93be-24ce637ad087)

             sudo yum install git

             ![image](https://github.com/user-attachments/assets/cf5d9272-1a62-4ec1-aace-ab4d17fed8aa)

              sudo git clone https://github.com/skl256/grafana_stack_for_docker.git

              ![image](https://github.com/user-attachments/assets/4bad62e0-b446-459d-80b5-6c764e3814ce)

               cd grafana_stack_for_docker

![image](https://github.com/user-attachments/assets/c8df7138-fd82-4a18-9acb-9d6d1045dab4)

 sudo mkdir -p /mnt/common_volume/swarm/grafana/config

 sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data,loki-data,promtail-data}

 sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana}

  sudo touch /mnt/common_volume/grafana/grafana-config/grafana.ini

   sudo touch /mnt/common_volume/grafana/grafana-config/grafana.ini

    sudo cp config/* /mnt/common_volume/swarm/grafana/config/

     sudo mv grafana.yaml docker-compose.yaml

![image](https://github.com/user-attachments/assets/b6e4bda5-4e94-46ed-b03f-28de5749ac65)

 sudo docker compose up -d

 ![image](https://github.com/user-attachments/assets/7e9163df-fbbf-4e3e-9f90-e87442683f9d)




 • переходим на сайт localhost:3000

            User & Password GRAFANA: admin

            Код графаны: 3000

            Код прометеуса: http://prometheus:9090
• в меню выбираем вкладку Dashboards и создаем Dashboard

            ждем кнопку +Add visualization, а после "Configure a new data source"

            выбираем Prometheus

            Connection

            http://prometheus:9090
• Authentication

            Basic authentication

            User: admin

            Password: admin

            Нажимаем на Save & test и должно показывать зелёную галочку
• в меню выбираем вкладку Dashboards и создаем Dashboard

            ждем кнопку "Import dashboard"

            Find and import dashboards for common applications at grafana.com/dashboards: 1860 //ждем кнопку Load

            Select Prometheus ждем кнопку "Import"

![image](https://github.com/user-attachments/assets/812c5d43-32ae-4178-ad4f-5f5efa6e4d60)



Захом в connection там где мы писали http://prometheus:9090 пишем http://victoriametrics:8428 И заменяем имя из "Prometheus-2" в "Vika" нажимаем на dashboards add visualition выбираем "Vika" снизу меняем на "code" Переходим в терминал и пишем

 echo -e "# TYPE OILCOINT_metric1 gauge\nOILCOINT_metric1 0" | curl --data-binary @- http://localhost:8428/api/v1/import/prometheus

  команда отправляет бинарные данные (например, метрики в формате Prometheus) на локальный сервер, который слушает на порту 8428.

 curl -G 'http://localhost:8428/api/v1/query' --data-urlencode 'query=OILCOINT_metric1'

![image](https://github.com/user-attachments/assets/85ff8297-c57f-4cdb-a9e7-dd374ce0408e)

Копируем переменную OILCOINT_metric1 и вставляем в query

Нажимаем run

![image](https://github.com/user-attachments/assets/1495962c-9f04-4797-976c-dfa69e7bee4c)

Копируем переменную OILCOINT_metric1 и вставляем в code

![image](https://github.com/user-attachments/assets/4e652323-b27f-4308-84f0-ca1b49be7e4d)











            







             



         

        

        



        
      






      
