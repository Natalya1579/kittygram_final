
![Main Kittygram workflow](https://github.com/github/docs/actions/workflows/main.yml/badge.svg)

### Описание

- Проект "Контейнеры и CI/CD для Kittygram" создан в рамках учебного курса Яндекс Практикум, содержит настройки запуска проекта в контейнерах, автоматического тестирования и деплой этого проекта на удалённый сервер.
- Kittygram — социальная сеть для обмена фотографиями любимых питомцев. Проект состоит из бэкенд-приложения на Django и фронтенд-приложения.

### Функции
* регистрация пользователей
* добавление нового питомца
* изменение/удаление своего питомца
* добавление достижения питомца


### Стек использованных технологий
* Django==3.2.3  
* djangorestframework==3.12.4
* djoser==2.1.0
* webcolors==1.11.1
* psycopg2-binary==2.9.3
* Pillow==9.0.0
* pytest==6.2.4
* pytest-django==4.4.0
* pytest-pythonpath==0.7.3
* PyYAML==6.0
* flake8==6.0.0
* flake8-isort==6.0.0
* python-dotenv==1.0.1

### Установка
Как развернуть проект на локальной машине:

1. Клонировать репозиторий:
```
git clone git@github.com:Natalya1579/kittygram_final.git
```
2. Перейти в клонированный репозиторий в командной строке:
```
cd kittygram_final
```
3. Создать виртуальное окружение:
```
python3 -m venv venv
```
4. Активировать вирутальное окружение:
```
source venv/bin/activate
```
5. Установить зависимости из файла requirements.txt:
```
python3 -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```
6. Выполнить миграции:
```
python3 manage.py migrate
```
7. Запустить проект:
```
python3 manage.py runserver
```

### Файл `.env` с переменными окружения
Вписать в него переменные для инициализации БД и связи с ней.

```
POSTGRES_USER=django_user
POSTGRES_PASSWORD=mysecretpassword
POSTGRES_DB=django
```

где:
* POSTGRES_USER — имя пользователя БД (необязательная переменная, значение по умолчанию — postgres);
* POSTGRES_PASSWORD — пароль пользователя БД (обязательная переменная для создания БД в контейнере);
* POSTGRES_DB — название базы данных (необязательная переменная, по умолчанию совпадает с POSTGRES_USER).


### Требования по выполнению проекта:

####  Как работать с репозиторием финального задания

##### Что нужно сделать

Настроить запуск проекта Kittygram в контейнерах и CI/CD с помощью GitHub Actions

##### Как проверить работу с помощью автотестов

В корне репозитория создайте файл tests.yml со следующим содержимым:
```yaml
repo_owner: ваш_логин_на_гитхабе
kittygram_domain: полная ссылка (https://доменное_имя) на ваш проект Kittygram
taski_domain: полная ссылка (https://доменное_имя) на ваш проект Taski
dockerhub_username: ваш_логин_на_докерхабе
```

Скопируйте содержимое файла `.github/workflows/main.yml` в файл `kittygram_workflow.yml` в корневой директории проекта.

Для локального запуска тестов создайте виртуальное окружение, установите в него зависимости из backend/requirements.txt и запустите в корневой директории проекта `pytest`.

##### Чек-лист для проверки перед отправкой задания

- Проект Taski доступен по доменному имени, указанному в `tests.yml`.
- Проект Kittygram доступен по доменному имени, указанному в `tests.yml`.
- Пуш в ветку main запускает тестирование и деплой Kittygram, а после успешного деплоя вам приходит сообщение в телеграм.
- В корне проекта есть файл `kittygram_workflow.yml`.


Автор: Бугаева Н.