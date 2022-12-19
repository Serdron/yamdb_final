![example workflow](https://github.com/Serdron/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

Проект запущен по адресу: yatpract.sytes.net

# api_yamdb
### Описание
Api_yamdb — это сервис о музыке, фильмах и книгах. На нем вы сможете узнать рейтинги популярных произведений поставить им оценки, написать рецензии и комментарии к ним.
____
### Технологии
- Python 3.7
- Django==2.2.16
- djangorestframework==3.12.4
- Docker 20.10.21
- Postgres 13.0
- NGNIX 1.21.3
____
### Шаблон наполнения env-файла (infra/.env),

DB_ENGINE=django.db.backends.postgresql # работаем с postgresql
DB_NAME=postgres # имя базы данных
POSTGRES_USER=user # логин для подключения к базе данных
POSTGRES_PASSWORD=password # пароль для подключения к БД 
DB_HOST=db # название сервиса
DB_PORT=5432 # порт для подключения к БД 
____
### Запуск проекта
В командной строке в папке /infra 
docker-compose up -d # Собирает образы и запускает сервер
docker-compose exec web python manage.py migrate # Выполнение миграций БД
docker-compose exec web python manage.py createsuperuser # Создание Суперюзера
docker-compose down # Позволяет остановить сервер
____
### Работа с БД
docker-compose exec web python manage.py dumpdata > fixtures.json # Создание бэкапа БД
docker-compose cp ./fixtures.json web:./app # Добавление бэкапа в контейнер
docker-compose exec web python manage.py loaddata fixtures.json # Восстановление данных из бэкапа
____
### Запросы
- Для подробной информации по запросам: http://localhost/redoc
____
### Автор
- [Андрей Ростовцев](https://github.com/Serdron)
