# Система мониторинга Zabbix - Розаев А.Ю.

### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. Для проверки домашнего задания преподавателем в личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в чате учебной группы и/или в разделе “Вопросы по заданию” в личном кабинете.

Желаем успехов в выполнении домашнего задания!
 
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

![Zabbix login](https://github.com/expgt/netzabbix1hw/blob/main/zabbix_login.png)


`sudo apt update`

`sudo apt install postgresql`

`wget https://repo.zabbix.com/zabbix/7.0/debian/pool/main/z/zabbix-release/zabbix-release_latest_7.0+debian13_all.deb`

`dpkg -i zabbix-release_latest_7.0+debian13_all.deb`

`apt update`

`apt install zabbix-server-pgsql zabbix-frontend-php php8.4-pgsql zabbix-apache-conf zabbix-sql-scripts`

`sudo -u postgres createuser --pwprompt zabbix`

`sudo -u postgres createdb -O zabbix zabbix`

`zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix`

`sudo nano /etc/zabbix/zabbix_server.conf`

`sudo systemctl restart zabbix-server apache2`

`sudo systemctl enable zabbix-server apache2`


---

### Задание 2

![Hosts](https://github.com/expgt/netzabbix1hw/blob/main/hosts.png)
![Agent log](https://github.com/expgt/netzabbix1hw/blob/main/agent_log.png)
![Data](https://github.com/expgt/netzabbix1hw/blob/main/data.png)


`wget https://repo.zabbix.com/zabbix/7.0/debian/pool/main/z/zabbix-release/zabbix-release_latest_7.0+debian13_all.deb`

`dpkg -i zabbix-release_latest_7.0+debian13_all.deb`

`apt update`

`apt install zabbix-agent`

`systemctl restart zabbix-agent`

`systemctl enable zabbix-agent`

`sudo nano /etc/zabbix/zabbix_agentd.conf`

`sudo systemctl restart zabbix-agent.service`

`sudo systemctl status zabbix-agent.service`

`sudo tail -f /var/log/zabbix/zabbix_agentd.log`


---

### Задание 3


---

### Задание 4

