//Можно скачать git прямо из командной строки прописав Y

git clone https://github.com/skl256/grafana_stack_for_docker.git
//выдаст ошибку и предложит скачать git
~!чтобы проверить наличие папки использовать команду "ls"

cd grafana_stack_for_docker - переход в папку

sudo mkdir -p /mnt/common_volume/swarm/grafana/config - ничего не покажет

sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data,loki-data,promtail-data} - ничего не покажет

sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana} - ничего не покажет

touch /mnt/common_volume/grafana/grafana-config/grafana.ini - ничего не покажет

cp config/* /mnt/common_volume/swarm/grafana/config/ - ничего не покажет

mv grafana.yaml docker-compose.yaml -  переимонование файла (графана яму) в (докер компос Яму), но можно проверить при помощи команды ls
// Если не срабатывает, то проверить localhost в командной строке, должно быть [lapashiw@localhost grafana_stack_for_docker]$

...

sudo docker compose up -d