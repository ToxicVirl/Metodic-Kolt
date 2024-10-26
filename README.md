# Toxic гайдыч на Docker и Docker Compose

![image](https://github.com/user-attachments/assets/100935a5-561f-4dcb-a0e7-abac54091a87)


* Клонирование репозитория Grafana Stack для Docker с GitHub # https://github.com/skl256/grafana_stack_for_docker.git

* копируем команды

  git clone https://github.com/skl256/grafana_stack_for_docker.git # Клонирование репозитория Grafana Stack для Docker с GitHub.
  
  cd grafana_stack_for_docker # Переход в каталог, куда был склонирован репозиторий.

![image](https://github.com/user-attachments/assets/6747b311-4286-46c3-b546-83b08e5b6c7a)

 cd grafana_stack_for_docker # Переход в каталог, куда был склонирован репозиторий.

  ![image](https://github.com/user-attachments/assets/619f888f-e5a4-4333-a834-615a2253c9a5)

  sudo mkdir -p /mnt/common_volume/swarm/grafana/config # Создание каталога для конфигурации Grafana внутри общей директории в Docker Swarm.

![image](https://github.com/user-attachments/assets/71720060-02cb-48be-9d89-8a1db5d2a746)

 sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data,loki-data,promtail-data} # Создание нескольких директорий для хранения данных конфигурации и информации для Grafana, Prometheus, Loki, Promtail.

![image](https://github.com/user-attachments/assets/fffd73c6-5231-482c-a6d1-0fed845da4a9)

 sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana} № Изменение владельца этих директорий на текущего пользователя с помощью команд id -u и id -g, которые возвращают UID и GID текущего пользователя.

![image](https://github.com/user-attachments/assets/4c297ea4-2eeb-4a1c-b1ca-00191a28483f)

 touch /mnt/common_volume/grafana/grafana-config/grafana.ini # Создание пустого файла grafana.ini для дальнейшей конфигурации Grafana.

 ![image](https://github.com/user-attachments/assets/8f9e73d9-a4cf-40cd-a4b0-197cc745f892)

 cp config/* /mnt/common_volume/swarm/grafana/config/ # Копирование всех файлов из локальной директории config в созданный каталог конфигурации.

![image](https://github.com/user-attachments/assets/74ac2ce7-7c9b-4dda-a620-026cf80d262d)

mv grafana.yaml docker-compose.yaml # Переименование файла grafana.yaml в docker-compose.yaml, который используется для запуска контейнеров Docker через Docker Compose.

![image](https://github.com/user-attachments/assets/6f2b687b-c808-4b4c-b10a-febd78ae6a26)

yum install curl # Установка утилиты curl (на CentOS/RHEL) для выполнения HTTP-запросов.

![image](https://github.com/user-attachments/assets/4846fb50-2e40-4a7a-b86b-11dd091bf965)

COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4) # Использование команды curl для получения последней версии Docker Compose с GitHub API. Фильтрация ответа для извлечения тега с версией.

![image](https://github.com/user-attachments/assets/6b806cac-3fa7-4489-815c-14ce1b839abd)

curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose # Загрузка последней версии Docker Compose с официального репозитория GitHub и сохранение её в /usr/bin/docker-compose.

![image](https://github.com/user-attachments/assets/8f6810b1-c165-4e7d-a2de-24cdeb1bfe87)

sudo chmod +x /usr/bin/docker-compose # Предоставление прав на выполнение файла docker-compose.

![image](https://github.com/user-attachments/assets/c0f9a65e-4833-4f2d-9ac9-7409a7192311)

docker-compose --version

![image](https://github.com/user-attachments/assets/db2a76ad-c8d7-486f-a4b6-7c0264bdd94b)





 


