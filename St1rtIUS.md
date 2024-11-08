# Toxic гайдыч на Docker и Docker Compose

![image](https://github.com/user-attachments/assets/100935a5-561f-4dcb-a0e7-abac54091a87)

 Клонирование репозитория Grafana Stack для Docker с GitHub # https://github.com/skl256/grafana_stack_for_docker.git

 копируем команды

* Клонирование репозитория Grafana Stack для Docker с GitHub.

      git clone https://github.com/skl256/grafana_stack_for_docker.git 

![image](https://github.com/user-attachments/assets/6747b311-4286-46c3-b546-83b08e5b6c7a)

* Переход в каталог, куда был склонирован репозиторий.

      cd grafana_stack_for_docker
  
  ![image](https://github.com/user-attachments/assets/619f888f-e5a4-4333-a834-615a2253c9a5)

* Создание каталога для конфигурации Grafana внутри общей директории в Docker Swarm.
 
      sudo mkdir -p /mnt/common_volume/swarm/grafana/config 

![image](https://github.com/user-attachments/assets/71720060-02cb-48be-9d89-8a1db5d2a746)

* Создание нескольких директорий для хранения данных конфигурации и информации для Grafana, Prometheus, Loki, Promtail.

      sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data,loki-data,promtail-data}  

![image](https://github.com/user-attachments/assets/fffd73c6-5231-482c-a6d1-0fed845da4a9)

 * Изменение владельца этих директорий на текущего пользователя с помощью команд id -u и id -g, которые возвращают UID и GID текущего пользователя.

       sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana} 

![image](https://github.com/user-attachments/assets/4c297ea4-2eeb-4a1c-b1ca-00191a28483f)

* Создание пустого файла grafana.ini для дальнейшей конфигурации Grafana.

      touch /mnt/common_volume/grafana/grafana-config/grafana.ini 

 ![image](https://github.com/user-attachments/assets/8f9e73d9-a4cf-40cd-a4b0-197cc745f892)
 
 * Копирование всех файлов из локальной директории config в созданный каталог конфигурации.
 
       cp config/* /mnt/common_volume/swarm/grafana/config/ 

![image](https://github.com/user-attachments/assets/74ac2ce7-7c9b-4dda-a620-026cf80d262d)

* Переименование файла grafana.yaml в docker-compose.yaml, который используется для запуска контейнеров Docker через Docker Compose.

      mv grafana.yaml docker-compose.yaml 

![image](https://github.com/user-attachments/assets/6f2b687b-c808-4b4c-b10a-febd78ae6a26)

sudo yum install wget

//Скачиваем файл репозитория:
sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo
//Везде прописываем "Y"

![image](https://github.com/user-attachments/assets/e8c1a196-d807-4160-bae3-7711afddd348)

//Устанавливаем docker: (идёт долгая устоновкка так что скрина не будет, но всё дожнор нормально устоновиться)
sudo yum install docker-ce docker-ce-cli containerd.io

//Запускаем его и разрешаем автозапуск:
sudo systemctl enable docker --now

![image](https://github.com/user-attachments/assets/9e4eda0a-7f4b-4b22-88fa-5bf31b6a1cd9)


* Установка утилиты curl (на CentOS/RHEL) для выполнения HTTP-запросов.

      sudo yum install curl 

![image](https://github.com/user-attachments/assets/4846fb50-2e40-4a7a-b86b-11dd091bf965)\

* Использование команды curl для получения последней версии Docker Compose с GitHub API. Фильтрация ответа для извлечения тега с версией.

      COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)

![image](https://github.com/user-attachments/assets/6b806cac-3fa7-4489-815c-14ce1b839abd)

* Загрузка последней версии Docker Compose с официального репозитория GitHub и сохранение её в /usr/bin/docker-compose.

      sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose  

![image](https://github.com/user-attachments/assets/8f6810b1-c165-4e7d-a2de-24cdeb1bfe87)

* Предоставление прав на выполнение файла docker-compose.
 
      sudo chmod +x /usr/bin/docker-compose 
    
 ![image](https://github.com/user-attachments/assets/c0f9a65e-4833-4f2d-9ac9-7409a7192311)

      docker-compose --version

![image](https://github.com/user-attachments/assets/db2a76ad-c8d7-486f-a4b6-7c0264bdd94b)





 


