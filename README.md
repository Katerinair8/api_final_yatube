# Как запустить проект:

### Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/yandex-praktikum/kittygram.git
cd kittygram
```

### Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
source env/bin/activate
```
### Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
pip install -r requirements.txt
```
### Выполнить миграции:

```
python3 manage.py migrate
```
### Запустить проект:

```
python3 manage.py runserver
```
# Примеры запросов к API

### Создание публикаций

Запрос POST на эндпоинт ```http://127.0.0.1:8000/api/v1/posts/```
```
Payload:

{
  "text": "string_test",
}
```

Ответ
```
{
    "id": 1,
    "author": "admin",
    "text": "string_test",
    "pub_date": "2022-11-08T09:21:50.288509Z",
    "image": null,
    "group": null
}
```

### Получение публикации по id

Запрос GET
```
http://127.0.0.1:8000/api/v1/posts/1/
```

Ответ
```
{
    "id": 1,
    "author": "admin",
    "text": "string_test",
    "pub_date": "2022-11-08T09:21:50.288509Z",
    "image": null,
    "group": null
}
```
### Проверить JWT-токен

Запрос POST на эндпоинт ```http://127.0.0.1:8000/api/v1/jwt/verify/```
```
Payload:

{
  "token: "string",
}
```

Ответ ```Error 401```
```
{
    "detail": "Token is invalid or expired",
    "code": "token_not_valid"
}
```
