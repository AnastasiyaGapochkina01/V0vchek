# Go project
Дано приложение на golang https://github.com/AnastasiyaGapochkina01/go-http-db, которое реализует простой HTTP-сервер с записью и просмотром истории запросов в PostgreSQL. 
## Процесс работы
1) Пользователь делает HTTP-запрос к серверу (например, GET /test).
2) Приложение фиксирует данные запроса в таблице requests.
3) Сервер выбирает последние 10 запросов из базы.
4) Пользователь получает их в формате JSON.

## Задача
1) Запустить приложение в docker (+ docker compose):
  - multistage сборка
  - публиковать собранный image в container registry
  - у БД должен быть healthcheck
  - деплой осуществлять с помощью docker compose, который должен содержать сервисы
    - приложение
    - nginx (в проли reverse-proxy)
    - postgres
    - migrator
    ```
    migrator:
      image: postgres:15
      restart: on-failure
      environment:
        PGPASSWORD: postgres
      volumes:
        - ./migrations:/migrations
      command: >
        sh -c "while ! pg_isready -h db -U postgres; do sleep 1; done && psql -h db -U postgres -d app_db -f /migrations/001_init.sql"
    ```
2) Написать ansible роли для
  - установки docker
  - разворачивания приложения
3) Подключить развернутое приложение к мониторингу, создать базовые дашборды для всех сервисов
4) Написать bash-скрипт для бэкапов postgresql, настроить его выполнение в час ночи по МСК кажыдй день
