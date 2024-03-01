Здравствуйте!
------------------------------------------------------
Версия композера: Docker Compose version v2.24.7
------------------------------------------------------
И так я подготовил компосер файл с названием docker-compose.
Когда я пытался протестить локально 1 вое задание мне выдо ОШИБКУ:
 => ERROR [web builder  1/11] RUN apt update                                                                                                                                   4.5s
------
 > [web builder  1/11] RUN apt update:
0.196
0.196 WARNING: apt does not have a stable CLI interface. Use with caution in scripts.
0.196
0.562 Get:1 http://deb.debian.org/debian bookworm InRelease [151 kB]
0.821 Get:2 http://deb.debian.org/debian bookworm-updates InRelease [55.4 kB]
0.914 Get:3 http://deb.debian.org/debian-security bookworm-security InRelease [48.0 kB]
1.008 Get:4 http://deb.debian.org/debian bookworm/main amd64 Packages [8786 kB]
2.942 Reading package lists...
3.415 E: Release file for http://deb.debian.org/debian/dists/bookworm-updates/InRelease is not valid yet (invalid for another 14d 1h 40min 23s). Updates for this repository will not be applied.
3.415 E: Release file for http://deb.debian.org/debian-security/dists/bookworm-security/InRelease is not valid yet (invalid for another 14d 1h 11min 47s). Updates for this repository will not be applied.
------
failed to solve: process "/bin/sh -c apt update" did not complete successfully: exit code: 100
[root@localhost devops]#
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
РЕШЕНИЕ:
Я заменил в Dockerfile команду с RUN apt update на RUN apt upgrade
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Описание к заданию:Для запуска сервиса и тестов необходима база данных Postgres. Ее можно поднять локально или внутри docker. Для того, что бы передать сервису параметры подключения к базе данных можно использовать переменные окружения. Например:
DB_NAME=postgres
DB_USER=postgres
DB_PASSWORD=postgres
DB_HOST=127.0.0.1
DB_PORT=5432
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Задание 1:
Надо подготовить docker-compose.yml файл, который позволит собирать и запускать базу данных Postgres, выполнять все необходимые миграции и запускать сервис. Как результат этого шага я должен иметь возможность выполнить команду docker-compose build для сборки свежего образа сервиса. И docker-compose up для запуска сервиса. Посдле запуска в браузере по адресу http://localhost:8000/admin я должен увидить страницу с формой ввода логина и пароля. Порт на котором будет запущен сервис можете выбрать на ваше усмотрение.
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

