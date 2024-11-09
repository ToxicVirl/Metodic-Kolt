/mnt/common_volume/swarm/grafana/config/ - исправить targets: на exporter:9100
![image](https://github.com/user-attachments/assets/7b54df45-ae03-4118-a2b6-f276c63b3c03)
Важно

cd grafana_stack_for_docker

sudo docker compose up -d

пишем в строку поиска "http://localhost:3000" http://localhost:3000 User & Password GRAFANA: admin Код графаны: 3000 Код прометеуса: http://prometheus:9090

переходим на сайт localhost:3000 в меню выбираем вкладку Dashboards и создаем Dashboard ждем кнопку +Add visualization, а после "Configure a new data source" выбираем Prometheus

Connection http://prometheus:9090
