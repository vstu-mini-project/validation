# Сервис валидации документов
## Запуск для тестирования
1. Установить провайдер контейнеров [Docker](https://www.docker.com/)
2. Открыть директорию с проектом через терминал и выполнить команду
`docker-compose up -d --build`
3. Адреса сервисов
   1. React: `localhost:3000`
   2. Postgres: `localhost:5432`
   3. SpringBoot `localhost:8080/api`
4. Чтобы остановить все контейнеры `docker-compose down` или через интерфейс Docker Desktop.
## Запуск для разработки
1. Установить провайдер контейнеров [Docker](https://www.docker.com/)
### Frontend
1. Открыть директорию `/validation-backend` через терминал и выполнить команду
`docker-compose up -d --build`
2. Открыть директорию `/validation-frontend` через терминал и выполнить команду
`docker-compose up -d --build`
3. Чтобы остановить все контейнеры `docker-compose down` в каждой директории или через интерфейс Docker Desktop.
### Backend
1. Открыть директорию `/validation-backend` через терминал и выполнить команду
`docker-compose -f docker-compose.dev.yaml up  -d --build`
2. Запустить Spring Boot `src/main/java/com/validation`
3. Завершить работу контейнера Postgres
`docker-compose -f docker-compose.dev.yaml up  -d --build`
