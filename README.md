 1 устанавливает утилиту wget на вашу систему

       sudo yum install wget

![image](https://github.com/user-attachments/assets/908ec0e1-c1e6-4fbf-b22e-3e978b34d7f0)

2Скачиваем файл репозитория

      sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo

![image](https://github.com/user-attachments/assets/8065f64a-f195-429b-a6a9-04502fde822e)

3 Устанавливаем docker

      sudo yum install docker-ce docker-ce-cli containerd.io

![image](https://github.com/user-attachments/assets/0f79a9a4-f5d7-4260-aef8-65047e4919e4)

4 • Запускаем его и разрешаем автозапуск

      sudo systemctl enable docker --now


![image](https://github.com/user-attachments/assets/d94fccef-8646-40bc-a433-a09f3de7842b)

5 Запускаем его и разрешаем автозапуск

      sudo yum install curl

6 Объявление переменной COMVER, полученной в результате curl запроса, хранящей в себе номер последней версии Docker Compose      

COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4)


![image](https://github.com/user-attachments/assets/3e3f5c39-8997-4012-88a6-2d6ebff14d4f)

7 Теперь скачиваем скрипт docker-compose последней версии, используя объявленную ранее переменную и помещаем его в каталог /usr/bin

sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose


![image](https://github.com/user-attachments/assets/3823833a-25f7-4529-a680-8395c792674a)

8 Предоставление прав на выполнение файла docker-compose.

sudo chmod +x /usr/bin/docker-compose

9 Проверка установленной версии Docker Compose.

docker-compose --version

![image](https://github.com/user-attachments/assets/92b833a9-f5ee-4f92-8a45-ec1be0df51b3)

10 выдаст ошибку и предложит скачать git, согласиться и продолжить

git clone https://github.com/skl256/grafana_stack_for_docker.git

![image](https://github.com/user-attachments/assets/224234db-fec3-4bd8-a60b-ccb4ab1c199f)

11  переход в папку

cd grafana_stack_for_docker

 12 команда создаёт полный путь /mnt/common_volume/swarm/grafana/config, включая все необходимые промежуточные каталоги, если они ещё не существуют.
sudo mkdir -p /mnt/common_volume/swarm/grafana/config

 13 команда создаёт структуру каталогов для Grafana и связанных с ней компонентов, если они ещё не существуют.
 
sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data}

 14 все файлы и каталоги в указанных директориях будут переданы в собственность текущему пользователю и его группе
 
sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana} 

 15 файл grafana.ini уже существует, команда обновит его временные метки (время последнего доступа и изменения). Если файл не существует, команда создаст новый пустой файл с указанным именем по указанному пути.
 
 touch /mnt/common_volume/grafana/grafana-config/grafana.ini

 16 команда копирует все файлы и подкаталоги из директории config в директорию /mnt/common_volume/swarm/grafana/config/
 
cp config/* /mnt/common_volume/swarm/grafana/config/

 17 команда переименовывает файл grafana.yaml в docker-compose.yaml. Ничего не покажет, но можно проверить при помощи команды ls

mv grafana.yaml docker-compose.yaml 

18 команда создает и запускает контейнеры в фоновом режиме, используя конфигурацию из файла docker-compose.yml, с правами суперпользователя.\

sudo docker compose up -d

![image](https://github.com/user-attachments/assets/7789f01b-4f72-4531-908c-321e391abe6a)

18 команда создает и запускает контейнеры в фоновом режиме, используя конфигурацию из файла docker-compose.yml, с правами суперпользователя.

 sudo docker compose up -d

![image](https://github.com/user-attachments/assets/512c5ed7-ca1d-4090-b7d2-a096256d2071)

19  команда открывает файл docker-compose.yaml в текстовом редакторе vi с правами суперпользователя, что позволяет вам редактировать его содержимое.

 Нас перекинет в текстовый редактор

 Что-бы что-то изменить в тесковом редакторе нажмите insert на клавиатуре

 Что бы сохранить что-то в этом документе нажимаем Esc пишем :wq! В этом текставом редакторе мы должны поставить node-exporter после services
sudo vi docker-compose.yaml

 sudo vi docker-compose.yaml

![image](https://github.com/user-attachments/assets/25803f89-ab5d-461d-9c3f-9887c129f9df)

![image](https://github.com/user-attachments/assets/1afd62d0-1b7d-4f74-9de6-9b9bc7ed5e6c)


20 команда открывает файл prometheus.yaml в текстовом редакторе vi с правами суперпользователя.

/mnt/common_volume/swarm/grafana/config/prometheus.yaml - исправить targets: на exporter:9100

sudo vi prometheus.yaml 

![image](https://github.com/user-attachments/assets/7ab67d6d-1540-4cb0-bc67-3d7c5a5669d3)

![image](https://github.com/user-attachments/assets/fb8f88b4-26d8-42c9-8139-1adc4ee0003a)

















