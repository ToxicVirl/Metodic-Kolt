Важно
cd grafana_stack_for_docker 
sudo docker compose up -d
пишем в строку поиска "http://localhost:3000"
http://localhost:3000
User & Password GRAFANA: admin
Код графаны: 3000
Код прометеуса: http://prometheus:9090

переходим на сайт localhost:3000
в меню выбираем вкладку Dashboards и создаем Dashboard
ждем кнопку +Add visualization, а после "Configure a new data source"
выбираем Prometheus

Connection
http://prometheus:9090

Authentication
Basic authentication
User: admin
Password:admin
---------------------------------------------
в меню выбираем вкладку Dashboards и создаем Dashboard
ждем кнопку "Import dashboard"
Find and import dashboards for common applications at grafana.com/dashboards: 1860  //ждем кнопку Load
Select Prometheus
ждем кнопку "Import"
