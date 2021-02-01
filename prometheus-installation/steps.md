
Switch to root:
> sudo -i  

Update the machine for changes:
> apt update

Create user group for prometheus: 
> useradd -M -s /bin/false prometheus

Create a directory 'prometheus' by:
> mkdir /etc/prometheus

Create another directory with the name 'prometheus' under lib/ :
> mkdir /var/lib/prometheus

Change permision of the directories created:
> chown prometheus:prometheus /var/lib/prometheus

> chown prometheus:prometheus /etc/prometheus

Go to directory 'tmp' by:
> cd /tmp

Get latest prometheus from [here](https://prometheus.io/download/):
> wget https://github.com/prometheus/prometheus/releases/download/v2.24.1/prometheus-2.24.1.linux-amd64.tar.gz

Uncompress the files by:
> tar xvf prometheus-2.24.1.linux-amd64.tar.gz

Copy files to diffrent location by:
> cp prometheus-2.24.1.linux-amd64/prometheus /usr/local/bin/

> cp prometheus-2.24.1.linux-amd64/promtool /usr/local/bin/

Change the permission by:
> chown prometheus:prometheus /usr/local/bin/prometheus

> chown prometheus:prometheus /usr/local/bin/promtool

Copy directories from the extracted folder by:
> cp -r prometheus-2.24.1.linux-amd64/consoles /etc/prometheus/

> cp -r prometheus-2.24.1.linux-amd64/console_libraries /etc/prometheus/

Give proper permission by:
> chown -R prometheus:prometheus /etc/prometheus/

> chown -R prometheus:prometheus /etc/prometheus/console_libraries

> cp -r prometheus-2.24.1.linux-amd64/prometheus.yml /etc/prometheus/

Check the content of 'prometheus.yml' file by:
> cat prometheus-2.24.1.linux-amd64/prometheus.yml

Go to the directory 'system' :
> cd /etc/systemd/system

Copy the content of [prometheus.service](prometheus.service) :
> nano prometheus.service

Reload the daemon to take changes effect:
> systemctl daemon-reload

Start the prometheus by:
> systemctl start prometheus

If the prometheus is disabled then enable it by:
> systemctl enable prometheus

Check the status of prometheus:
> systemctl status prometheus