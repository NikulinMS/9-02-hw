# Домашнее задание к занятию "`9.2. Zabbix. Часть 1 - Никулин Михаил`

---
### Задание 1

![admin_zabbix.png](img%2Fadmin_zabbix.png)

```
- wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4%2Bdebian11_all.deb
- dpkg -i zabbix-release_6.0-4+debian11_all.deb
- apt update
- apt install zabbix-server-pgsql zabbix-frontend-php php7.4-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
- sudo apt install postgresql
- su - postgres -c 'psql --command "CREATE USER zabbix WITH PASSWORD '\'123456789\'';"'
- su - postgres -c 'psql --command "CREATE DATABASE zabbix OWNER zabbix;"'
- zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
- sed -i 's/# DBPassword=/DBPassword=123456789/g' /etc/zabbix/zabbix_server.conf
- sudo systemctl restart zabbix-server apache2 # zabbix-agent
- sudo systemctl enable zabbix-server apache2 # zabbix-agent
```

---

### Задание 2

![zabbix_hosts.png](img%2Fzabbix_hosts.png)
![hosts_latest_data.png](img%2Fhosts_latest_data.png)
![host_logs.png](img%2Fhost_logs.png)

```
- wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-4%2Bdebian11_all.deb
- dpkg -i zabbix-release_6.0-4+debian11_all.deb
- apt update
- sudo apt install zabbix-agent -y
- sudo systemctl restart zabbix-agent
- sudo systemctl enable zabbix-agent
- sed -i 's/Server=127.0.0.1/Server=192.168.1.67/g' /etc/zabbix/zabbix_agentd.conf
- sed -i 's/ServerActive=127.0.0.1/ServerActive=192.168.1.67/g' /etc/zabbix/zabbix_agentd.conf
- sudo systemctl restart zabbix-agent
```

---

### Задание 3*


