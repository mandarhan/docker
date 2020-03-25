# Mandarhan Docker

Готовая конфигурация для production сервера для **Mandarhan Hotel
Management System** (далее **MHMS**). В роли проксирующего
сервера используется Caddy, при желании можно заменить.

Сервер БД используется PostgreSQL не старше 10 версии. Не обязательно
БД понимать также в контейнере, вы можете использовать лубую
PostgreSQL совместимую базу, главное не забудьте указать верные
параметры подключения к БД в файле `.env`.

## Установка

1. `$ git clone https://github.com/mandarhan/docker.git mandarhan`
2. `$ cd mandarhan`
3. `$ cp example.env .env`
4. Измените настройки окружения под свои нужды.
5. `$ docker-compose run mandarhan init`

Вы можете не использовать данный репозиторий, достаточно 
написать правильный конфиг для docker-compose, чтобы в нём
использовался билд MHMS.

### Настройка Caddy

Настройка подробно описание здесь: https://github.com/Drivetech/django-caddy

Также в issue есть описание использовать плагины: https://github.com/Drivetech/django-caddy/issues/28

### Настройка MHMS

Для настройки окружения используется `.env` файл. В файле
`example.env` используются минимальный набор необходимых
переменных окружения. 

**ВНИМАНИЕ!** Если вы используете PostgreSQL в контейнере, тогда
не меняйте переменную `POSTGRES_HOST`.

## Обновление

1. `$ git pull` _(опционально)_
2. `$ docker-compose pull mandarhan`
3. `$ docker-compose run mandarhan update` 

## Запуск сервера

`$ docker-compose up -d`
