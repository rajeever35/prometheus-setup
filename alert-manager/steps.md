> cd /tmp

> wget https://github.com/prometheus/alertmanager/releases/download/v0.21.0/alertmanager-0.21.0.linux-amd64.tar.gz

> tar -xvzf alertmanager-0.21.0.linux-amd64.tar.gz

> mv alertmanager-0.21.0.linux-amd64/alertmanager /usr/local/bin/

> mkdir /etc/alertmanager/

Copy the content from [here](alertmanager.yml)
> nano /etc/alertmanager/alertmanager.yml

Copy the content from [here](rules.yml)
> nano /etc/prometheus/alert_rules.yml

Copy the content from [here](alertmanager.service)
> nano /etc/systemd/system/alertmanager.service

Copy the content from [here](prometheus.yml)
> nano /etc/prometheus/prometheus.yml

> systemctl daemon-reload

> systemctl start alertmanager

> systemctl status alertmanager