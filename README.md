# 12-6-Git

Домашнее задание к занятию 12.6 «Репликация и масштабирование. Часть 1» - Сергей Григорьев

Задание 1
На лекции рассматривались режимы репликации master-slave, master-master, опишите их различия.

При использовании репликации master-slave:
master -  основной сервер БД, на нём происходит вся обработка данных
slave - вспомогательный сервер БД. Он копирует данные с master. Со slave-серверов происходит только чтение данных. Количество - любое.

При использовании репликации master-master:
каждый сервер является одновременно и master и slave сервером для других аналогичных серверов.

Задание 2
Выполните конфигурацию master-slave репликации, примером можно пользоваться из лекции.
Приложите скриншоты конфигурации, выполнения работы: состояния и режимы работы серверов.

Устанавливаем mysql на master и slave ВМ
Master – 10.0.2.15 – SQL master 1
Slave – 10.0.2.4 – SQL slave
![1-1](https://github.com/SG-netology/12-6-Git/blob/main/1-1.png)
![1-2](https://github.com/SG-netology/12-6-Git/blob/main/1-2.png)

Скриншоты конфигурации
![1-3](https://github.com/SG-netology/12-6-Git/blob/main/1-3.png)
![1-4](https://github.com/SG-netology/12-6-Git/blob/main/1-4.png)

На master создаем пользователя repa (права и статус master)
![1-5](https://github.com/SG-netology/12-6-Git/blob/main/1-5.png)

На slave определяем источник данных
![1-6](https://github.com/SG-netology/12-6-Git/blob/main/1-6.png)

Запуск журнала регистрации
![1-7](https://github.com/SG-netology/12-6-Git/blob/main/1-7.png)

Создаем на master новую базу (examplebase)
![1-8](https://github.com/SG-netology/12-6-Git/blob/main/1-8.png)

Проверяем, что она появилась на slave
![1-9](https://github.com/SG-netology/12-6-Git/blob/main/1-9.png)
