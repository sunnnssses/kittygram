[![Main Kittygram Workflow](https://github.com/sunnnssses/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/sunnnssses/kittygram_final/actions/workflows/main.yml)

# Kittygram

## Описание проекта
Kittygram — это сервис, с помощью которого вы можете делиться фотографиями и достижениями своих котиков!

## Стек
- Python 3.9
- Django 3.2.16
- Nginx
- Docker

## Как развернуть проект
Клонировать репозиторий и перейти в него в командной строке:
```
git clone https://github.com/sunnnssses/kittygram_final
```
```
cd kittygram_final
```
Выполнить запуск командой
```
sudo docker compose -f docker-compose.production.yml up -d
```
После запуска применить миграцию
```
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
```
Выполнить сбор статики
```
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/
```
## Заполнение .env
Для работы проекта необходимо создать и заполнить файл .env следующими переменными окружения:
- POSTGRES_DB=kittygram
- POSTGRES_USER=kittygram_user
- POSTGRES_PASSWORD=kittygram_password
- DB_HOST=db
- DB_PORT=5432
- SECRET_KEY = 'secret_key'
- DEBUG = False

##### Автор: sunnnssses
