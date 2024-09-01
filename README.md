# Система сбора данных о товарах с Wildberries

## Описание проекта

Этот проект представляет собой систему, состоящую из двух микросервисов и базы данных, которая предназначена для получения и хранения актуальной информации о товарах с сайта wildberries.ru.

### Основные функции системы:
- Получение информации о товарах (ID товара, цена, размеры, остатки на складах).
- Хранение запрошенных данных в базе данных.
- Автоматическое обновление данных каждые 5 минут.
- Возможность получения информации через Телеграм-бот.

### Используемые технологии:
- Python 3.10+
- FastAPI 0.100+
- Pydantic 2.0+
- PostgreSQL 14.0+
- SQLAlchemy 2 + Alembic
- Aiogram 2+
- Docker, docker-compose
- Celery

## Структура проекта

Проект состоит из двух микросервисов:

1. **Микросервис 1 (fastapi)**: 
    - Отвечает за хранение и обработку данных о товарах.
    - Предоставляет API для получения информации о товарах.
    - Автоматически обновляет данные каждые 5 минут.
    - Данные хранятся в PostgreSQL.

2. **Микросервис 2 (Телеграм-бот)**: 
    - Отвечает за взаимодействие с пользователем через Telegram.
    - Принимает запросы на получение информации о товарах по их ID.
    - Возвращает пользователю актуальные данные.

## Быстрый старт

### Предварительные требования

Перед запуском убедитесь, что на вашем компьютере установлены следующие компоненты:

- Docker
- Docker Compose

### Запуск проекта

1. Клонируйте репозиторий:

    ```bash
    git clone git@github.com:artemon1981/bears_test.git
    cd bears_test
    ```

2. Создайте файл `.env` на основе примера `.env.example` и заполните необходимыми данными.

3. Соберите и запустите все контейнеры:

    ```bash
    docker-compose up --build
    ```

4. Теперь сервис доступен по адресу `http://fastapi:8000`, а Телеграм-бот готов к взаимодействию с пользователями.

## Документация

### API микросервиса 1 (fastapi)

API доступно по адресу `/docs` после запуска микросервиса. Используйте его для проверки работы эндпоинтов и взаимодействия с системой.
