
Switch to root

> sudo -i  

> apt update

Create user group for prometheus 
> useradd -M -s /bin/false prometheus

> mkdir /etc/prometheus

> mkdir /var/lib/prometheus

> chown prometheus:prometheus /var/lib/prometheus

> chown prometheus:prometheus /etc/prometheus

> cd /tmp

> wget https://github.com/prometheus/prometheus/releases/download/v2.24.1/prometheus-2.24.1.linux-amd64.tar.gz

> tar xvf prometheus-2.24.1.linux-amd64.tar.gz

> cp prometheus-2.24.1.linux-amd64/prometheus /usr/local/bin/

> cp prometheus-2.24.1.linux-amd64/promtool /usr/local/bin/

> chown prometheus:prometheus /usr/local/bin/prometheus

> chown prometheus:prometheus /usr/local/bin/promtool

> cp -r prometheus-2.24.1.linux-amd64/consoles /etc/prometheus/

> cp -r prometheus-2.24.1.linux-amd64/console_libraries /etc/prometheus/

> chown -R prometheus:prometheus /etc/prometheus/

> chown -R prometheus:prometheus /etc/prometheus/console_libraries

> cp -r prometheus-2.24.1.linux-amd64/prometheus.yml /etc/prometheus/

> cat prometheus-2.24.1.linux-amd64/prometheus.yml

> cd /etc/systemd/system

> nano prometheus.service

> systemctl daemon-reload

> systemctl start prometheus

> systemctl enable prometheus

> systemctl status prometheus