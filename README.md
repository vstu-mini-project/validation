# Сервис валидации документов
## Как установить Docker
1. Скачать [Docker](https://www.docker.com/) с официального сайта.
2. Запустить установщик от имени администратора.
3. Перезагрузить компьютер.
4. Запустить Docker. Если возникает ошибка связянная с WSL:
   1. Запустить терминал от имени администратора (Поиск -> cmd)
   2. Выполнить команду `wsl.exe --update`
5. Docker должен быть в состоянии Running. Если Docker не пишет Stopping, то все нормально.
## Клонирование репозитория
1. Установить [Git](https://git-scm.com/).
2. Открыть директорию в которую вы хотите загрузить папку с проектом через терминал (правой кнопкой -> GIT Bash Here).
3. Выполнить команду `git clone https://github.com/vstu-mini-project/validation.git`. Это создаст папку validation в этой директории.
4. Открыть папку с проектом командой `cd ./validation` и выполнить команды по очереди
```
git submodule init
git submodule update
```
5. В зависимости от задач перейти к следующему пункту.
## Запуск для тестирования
1. Установить провайдер контейнеров [Docker](https://www.docker.com/)
2. Открыть директорию с проектом через терминал и выполнить команду
`docker-compose up -d --build`
3. После выполнения команды и загрузки всех модулей (флаги done), проверить адреса в браузере.
   1. React: `localhost:3000`
   2. Postgres: `localhost:5432` - пока нет интерфейса
   3. SpringBoot `localhost:8080/api` - корень api, чтобы увидеть данные нужно указать репозиторий, например, `localhost:8080/api/students`
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
