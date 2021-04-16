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

![code](https://user-images.githubusercontent.com/28298006/115064213-0e42c400-9ec3-11eb-8332-03afc9abe83f.png)


3 - Start Heartbeat

The setup command loads the Kibana index pattern.

sudo heartbeat setup
sudo service heartbeat-elastic start


Após e so acessar o Kibana na seção:

Observability > Uptime

![observa](https://user-images.githubusercontent.com/28298006/115062092-56141c00-9ec0-11eb-8bf4-d9852af0edce.png)

Após a tela seguinte será apresentada:

![uptime](https://user-images.githubusercontent.com/28298006/115061954-282ed780-9ec0-11eb-83b6-953f321a2a72.png)











