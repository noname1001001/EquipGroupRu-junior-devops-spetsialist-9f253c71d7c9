Необходимо скачать репозиторий на хостовую машину
Затем выполнить команды поочередно: 
docker-compose build
docker-compose run composer install
docker-compose run node npm install
docker-compose run artisan key:generate
docker-compose run artisan migrate:fresh --seed
Последняя команда по репликации БД не сработала, скорее всего, я неправильно понял, каково должно быть между ними взаимодействие
После этого требуется запустить контейнеры в detached режиме:
docker-compose up -d
Подключиться к в веб-серверу можно по адресу localhost:8000
Решение не работает из-за неудавшейся репликации, но задача мне показалась интересной, поэтому попрошу подсказать, как это можно было сделать лучше. Про сбор метрик и мониторинг тоже было бы интересно. спасибо
