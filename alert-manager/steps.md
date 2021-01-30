Go to 'tmp' directory:
> cd /tmp

Download the latest alertmanager from [here](https://prometheus.io/download/):
> wget https://github.com/prometheus/alertmanager/releases/download/v0.21.0/alertmanager-0.21.0.linux-amd64.tar.gz

Extract the files by:
> tar -xvzf alertmanager-0.21.0.linux-amd64.tar.gz

Move the alertmanager from extraceted folder to /usr/local/bin/ :
> mv alertmanager-0.21.0.linux-amd64/alertmanager /usr/local/bin/

Create new directory with the name alertmanager under /etc/ :
> mkdir /etc/alertmanager/

Copy the content from [here](alertmanager.yml)
> nano /etc/alertmanager/alertmanager.yml

Copy the content from [here](rules.yml)
> nano /etc/prometheus/alert_rules.yml

Copy the content from [here](alertmanager.service)
> nano /etc/systemd/system/alertmanager.service

Copy the content from [here](prometheus.yml)
> nano /etc/prometheus/prometheus.yml

Reload the alertmanager to take changes effect:
> systemctl daemon-reload

Start alertmanger:
> systemctl start alertmanager

Check the status of alertmanager by:
> systemctl status alertmanager