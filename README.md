# Kittygram
Проект Kittygram предназначен для публикации и чтения информации о котиках.

### Установка:
Клонировать репозиторий и перейти в него в командной строке:

```
git@github.com:VeraPetrenko/kittygram_final.git
cd kittygram_final
```


Запустить проект локально:
```
docker compose -f docker-compose.production.yml
```

Запустить проект на удаленном сервере:
- Перейти в директорию kittygram, выполнить команды по запуску контейнеров, применить миграции и собрать статику:
```
cd kittygram
sudo docker compose -f docker-compose.production.yml pull
sudo docker compose -f docker-compose.production.yml down
sudo docker compose -f docker-compose.production.yml up -d
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/static/. /backend_static/static/

```

Сайт будет доступен по домену:
<https://ktgrm.serveftp.com/>

### Основные технологии
- django3.2.3
- djangorestframework 3.12.4
- noip.com
- gunicorn
- nginx

### Авторы
Vera Petrenko & Yandex Practicum
