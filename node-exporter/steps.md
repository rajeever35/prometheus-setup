## Steps to install node_exporter

> cd /tmp

Download latest node_exporter from [here](https://prometheus.io/download/)
> wget https://github.com/prometheus/node_exporter/releases/download/v1.0.1/node_exporter-1.0.1.linux-amd64.tar.gz

Extract the files by:
> tar xvf node_exporter-1.0.1.linux-amd64.tar.gz

Move the extracted folder to the directory node_exporter:
> mv node_exporter-1.0.1.linux-amd64 node_exporter

Go to the directory 'system' by:
> cd /etc/systemd/system/

Copy the content of [node_exporter.service](node_exporter.service) to node_exporter.service
> nano node_exporter.service

Start node_exporter by:
> systemctl start node_exporter

Check the status by:
> systemctl status node_exporter

<br>

## Update the prometheus.yml file

Go to the directory prometheus:
> cd /etc/prometheus/

Copy the content of [prometheus.yml](prometheus.yml) to the prometheus server file:
> nano prometheus.yml

Check if the [prometheus](prometheus.yml) file is valid by:
> promtool check config prometheus.yml

Restart prometheus server:
> systemctl restart prometheus
