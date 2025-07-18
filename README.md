![Main Kittygram workflow](https://github.com/Shtraube/kittygram_final/actions/workflows/main.yml/badge.svg?event=push)

### Описание:

Kittygram. Сервис, предназначенный для публикации сведений о котах.
Позволяет продемонстрировать миру фото своего котика и его достижения.

### Как запустить проект локально:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/Shtraube/kittygram_final.git
```

```
cd kittygram_final
```

Cоздать и активировать виртуальное окружение:

```
<sub>Для Linux:</sub>
python3 -m venv env
source env/bin/activate
<sub>Для Windows:</sub>
python -m venv env
source env/scripts/activate
```

Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

### Как запустить проект локально в docker-контейнерах:

Выполнить команды:
- в директории backend:
```
docker build -t ludwigshtraube/kittygram_backend .
docker push ludwigshtraube/kittygram_backend
```

- в директории frontend:
```
docker build -t ludwigshtraube/kittygram_frontend .
docker push ludwigshtraube/kittygram_frontend
```

- в директории nginx:
```
docker build -t ludwigshtraube/kittygram_gateway .
docker push ludwigshtraube/kittygram_gateway
```
- в корневой директории проекта, где содержится файл docker-compose.yml:
```
docker compose up
```

### Примеры некоторых запросов:

GET
```
/api/cats/
/api/cats/{id}/
/api/achievements/
/api/achievements/{id}/
/api/users/
/api/users/me/
/api/users/{id}/
```
POST
```
/api/cats/
/api/achievements/
/api/users/
```
PATCH
```
/api/achievements/{id}/
/api/users/me/
/api/users/{id}/
```
DELETE
```
/api/cats/{id}/
/api/achievements/{id}/
/api/users/me/
/api/users/{id}/
```

### Использованные технологии:

- [Django 3.2.3](https://docs.djangoproject.com/en/5.2/releases/3.2.3/)
Основной фреймворк для работы с бэкендом проекта.
- [Django REST framework 3.12.4](https://www.django-rest-framework.org/community/3.12-announcement/#django-rest-framework-312)
Фреймворк, использованный для создания API проекта.
