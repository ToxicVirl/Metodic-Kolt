//Можно скачать git прямо из командной строки прописав Y

git clone https://github.com/skl256/grafana_stack_for_docker.git
//выдаст ошибку и предложит скачать git
~!чтобы проверить наличие папки использовать команду "ls"

![image](https://github.com/user-attachments/assets/8fbd1cec-2a7d-4589-8a66-124dc2b38d56)


cd grafana_stack_for_docker - переход в папку

![image](https://github.com/user-attachments/assets/6caea34b-0d58-4bea-b60a-a41ea3aef36b)


sudo mkdir -p /mnt/common_volume/swarm/grafana/config - ничего не покажет

![image](https://github.com/user-attachments/assets/e7a8794f-29dd-4631-820f-347aa203ff73)


sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data,loki-data,promtail-data} - ничего не покажет


![image](https://github.com/user-attachments/assets/595668ef-1840-47ca-99a3-af6f61473173)


sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana} - ничего не покажет*

touch /mnt/common_volume/grafana/grafana-config/grafana.ini - ничего не покажет


![image](https://github.com/user-attachments/assets/01ca193c-b0f4-4c27-9fd6-0787f561d4ac)


cp config/* /mnt/common_volume/swarm/grafana/config/ - ничего не покажет


![image](https://github.com/user-attachments/assets/568be450-3ea8-455c-9e07-945628969b96)


mv grafana.yaml docker-compose.yaml -  переимонование файла (графана яму) в (докер компос Яму), но можно проверить при помощи команды ls
// Если не срабатывает, то проверить localhost в командной строке, должно быть [lapashiw@localhost grafana_stack_for_docker]$


![image](https://github.com/user-attachments/assets/98c5884c-7137-4ac6-ad41-a7e59eb1d96f)


...

sudo docker compose up -d
Всё должно робить 
