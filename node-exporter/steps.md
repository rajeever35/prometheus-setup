~Node Exporter~

cd /tmp
wget https://github.com/prometheus/node_exporter/releases/download/v1.0.1/node_exporter-1.0.1.linux-amd64.tar.gz
mv node_exporter-1.0.1.linux-amd64 node_exporter
cd /etc/systemd/system/
vim node_exporter.service
systemctl start node_exporter
systemctl status node_exporter
