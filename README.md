# Elastic-Uptime


monitorando Urls com Elastic Heartbeat

A documentação de instalação pode ser verificada no proprio website da Elasti - https://www.elastic.co/pt/downloads/beats/heartbeat


Para fim de estudo vou colocar o passo a passo da intalação para Linux Ubuntu

To add the Beats repository for APT:

1 - Download and install Heartbeat

curl -L -O https://artifacts.elastic.co/downloads/beats/heartbeat/heartbeat-7.12.0-amd64.deb
sudo dpkg -i heartbeat-7.12.0-amd64.deb

2 - Edit the configuration

Após instalação necessario efetuar a configuração do arquivo heartbeat.yml que fica no meu caso em /etc/heartbeat/
heartbeat.yml

output.elasticsearch:
  hosts: ["<es_url>"]
  username: "elastic"
  password: "<password>"
setup.kibana:
  host: "<kibana_url>"

3 - Edit the configuration - Add monitors

Edit the heartbeat.monitors setting in the heartbeat.yml file.

heartbeat.monitors:
- type: http
  urls: ["<http://localhost:9200>"]
  schedule: "@every 10s"

4 - Start Heartbeat

The setup command loads the Kibana index pattern.

sudo heartbeat setup
sudo service heartbeat-elastic start


Após e so acessar o Kibana na seção:

Observability > Uptime

![uptime](https://user-images.githubusercontent.com/28298006/115061954-282ed780-9ec0-11eb-83b6-953f321a2a72.png)











