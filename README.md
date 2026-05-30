# Домашнее задание к занятию "`Система мониторинга Zabbix`" - `Солопов Антон`


### Инструкция по выполнению домашнего задания

   1. Сделайте `fork` данного репозитория к себе в Github и переименуйте его по названию или номеру занятия, например, https://github.com/имя-вашего-репозитория/git-hw или  https://github.com/имя-вашего-репозитория/7-1-ansible-hw).
   2. Выполните клонирование данного репозитория к себе на ПК с помощью команды `git clone`.
   3. Выполните домашнее задание и заполните у себя локально этот файл README.md:
      - впишите вверху название занятия и вашу фамилию и имя
      - в каждом задании добавьте решение в требуемом виде (текст/код/скриншоты/ссылка)
      - для корректного добавления скриншотов воспользуйтесь [инструкцией "Как вставить скриншот в шаблон с решением](https://github.com/netology-code/sys-pattern-homework/blob/main/screen-instruction.md)
      - при оформлении используйте возможности языка разметки md (коротко об этом можно посмотреть в [инструкции  по MarkDown](https://github.com/netology-code/sys-pattern-homework/blob/main/md-instruction.md))
   4. После завершения работы над домашним заданием сделайте коммит (`git commit -m "comment"`) и отправьте его на Github (`git push origin`);
   5. В личном кабинете прикрепите и отправьте ссылку на решение в виде md-файла в вашем Github.
   6. Любые вопросы по выполнению заданий спрашивайте в разделе “Вопросы по заданию” в личном кабинете.
   
Желаем успехов в выполнении домашнего задания!
   
### Дополнительные материалы, которые могут быть полезны для выполнения задания

1. [Руководство по оформлению Markdown файлов](https://gist.github.com/Jekins/2bf2d0638163f1294637#Code)

---

### Задание 1

`Ответ:`

![Начальное-окно-регистрации](https://github.com/ultrmlvn/zabbix1/blob/main/Снимок%20экрана%202026-05-27%20в%2022.56.21.png#:~:text=Снимок-,экрана,-2026%2D05%2D27)

```
sudo -s

      apt install postgresql

      wget https://repo.zabbix.com/zabbix/7.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_latest_7.0+ubuntu24.04_all.deb

      dpkg -i zabbix-release_latest_7.0+ubuntu24.04_all.deb
      apt update

      apt install zabbix-server-pgsql zabbix-frontend-php php8.3-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent


      sudo -u postgres createuser --pwprompt zabbix

      sudo -u postgres createdb -O zabbix zabbix

      zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix

```



---

### Задание 2

`Ответ:`

1. ![Агент-подключен](https://github.com/ultrmlvn/zabbix1/blob/main/Снимок%20экрана%202026-05-30%20в%2020.29.21.png)
2. ![Логи-агента](https://github.com/ultrmlvn/zabbix1/blob/main/Снимок%20экрана%202026-05-30%20в%2020.32.18.png)
3. ![Данные-агента1](https://github.com/ultrmlvn/zabbix1/blob/main/Снимок%20экрана%202026-05-30%20в%2020.34.20.png)
   ![Данные-агента2(локальный)](https://github.com/ultrmlvn/zabbix1/blob/main/Снимок%20экрана%202026-05-30%20в%2020.35.09.png)


4. `Агент установил сразу, вместе с сервером, по этому команда по его установки сверху`
```
sudo vi /etc/zabbix/zabbix_agentd.conf
sudo systemctl restart zabbix-agent
cat /var/log/zabbix/zabbix_agentd.log
```

