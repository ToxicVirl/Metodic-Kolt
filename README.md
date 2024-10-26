# Docker и Docker Compose

* Клонирование репозитория Grafana Stack для Docker с GitHub # https://github.com/skl256/grafana_stack_for_docker.git

* копируем команды

  git clone https://github.com/skl256/grafana_stack_for_docker.git # Клонирование репозитория Grafana Stack для Docker с GitHub.
  
  cd grafana_stack_for_docker # Переход в каталог, куда был склонирован репозиторий.

![image](https://github.com/user-attachments/assets/6747b311-4286-46c3-b546-83b08e5b6c7a)

* cd grafana_stack_for_docker # Переход в каталог, куда был склонирован репозиторий.

  ![image](https://github.com/user-attachments/assets/619f888f-e5a4-4333-a834-615a2253c9a5)

*sudo mkdir -p /mnt/common_volume/swarm/grafana/config # Создание каталога для конфигурации Grafana внутри общей директории в Docker Swarm.

![image](https://github.com/user-attachments/assets/71720060-02cb-48be-9d89-8a1db5d2a746)

*sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data,loki-data,promtail-data} # Создание нескольких директорий для хранения данных конфигурации и информации для Grafana, Prometheus, Loki, Promtail.

![image](https://github.com/user-attachments/assets/fffd73c6-5231-482c-a6d1-0fed845da4a9)

*sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana} № Изменение владельца этих директорий на текущего пользователя с помощью команд id -u и id -g, которые возвращают UID и GID текущего пользователя.

![image](https://github.com/user-attachments/assets/4c297ea4-2eeb-4a1c-b1ca-00191a28483f)

