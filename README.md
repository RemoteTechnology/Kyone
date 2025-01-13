<img src="https://avatars.githubusercontent.com/u/153977186?s=400&u=7268ad55ed694cec25c1467486710abb82bc9ad8&v=4" style="width: 10%">
<h2 style="color: #2c2c2c;">Remote Technology</h2>
<br>
<h3>Используемые технологии:</h3>
<ul>
    <li>
        <a href="#" style="color: #57bafb;">PHP 8.3 (Laravel 10)</a>
    </li>
    <li>
        <a href="#" style="color: #57bafb;">PostgreSQL 13</a>
    </li>
    <li>
        <a href="#" style="color: #57bafb;">MongoDB 4</a>
    </li>
    <li>
        <a href="#" style="color: #57bafb;">Dart 3.7 (Flutter 3.28)</a>
    </li>
    <li>
        <a href="#" style="color: #57bafb;">RabbitMQ</a>
    </li>
</ul>
<hr>
<h3 style="color: #2c2c2c;">Настройка окружения <small><b style="color: #57bafb;text-decoration: underline;text-decoration-color: #57bafb;">STAGING</b></small></h3>
<ul>
    <li>
        <p>
            <span style="color: #2c2c2c;">Создать/настроить конфиг, как минимум надо настроить подключение к БД:</span><br>
            <b style="color: #2c2c2c;">(sudo) cp .example.env .env</b><br>
        </p>
    </li>
    <br />
    <li>
        <p>
            <span style="color: #2c2c2c;">Поднять docker:</span><br>
            <b style="color: #2c2c2c;">
                <small>(sudo) docker-compose up --build -d</small>
            </b>
        </p>
    </li>
    <br />
    <li>
        <p>
            <span style="color: #2c2c2c;">Создать/настроить конфиг, для работы Laravel:</span><br>
            <b style="color: #2c2c2c;">cp sources/.env.example sources/.env</b><br>
            <small style="color: #57bafb;">Так же рекоммендуется создать коллекцию для журнала ошибок в монге. Удобно использовать <b style="color: #57bafb;">MongoDB Compass</b>.</small><br>
        </p>
    </li>
    <br />
    <li>
        <p>
            <span style="color: #2c2c2c;">Установить зависимости:</span><br>
            <b style="color: #2c2c2c;">(sudo) docker-compose run php-fpm composer --ignore-platform-req=ext-sockets install</b><br>
        </p>
    </li>
    <br />
    <li>
        <span style="color: #2c2c2c;">Создать миграции: <small style="color: #57bafb;">(Нужно проверить есть ли база)</small></span><br>
        <b style="color: #2c2c2c;">(sudo) docker-compose run php-fpm php artisan migrate</b><br>
    </li>
    <br />
    <li>
        <span style="color: #2c2c2c;">Сгенерировать CSRF токен:</span><br>
        <b style="color: #2c2c2c;">(sudo) docker-compose run php-fpm php artisan key:generate</b><br>
    </li>
    <br />
    <li>
        <span style="color: #2c2c2c;">Установить права и группу на директорию с проектом:</span><br>
        <b style="color: #2c2c2c;">sudo chmod -R 777 $PWD</b><br>
        <b style="color: #2c2c2c;">sudo chown -R <MY GROUP>:<MY GROUP> $PWD</b><br>
    </li>
    <br />
    <li>
        <span style="color: #2c2c2c;">Добавить почтовый сервер <small style="color: #57bafb;">(или хотя бы пароль, я использую smtp.yandex.ru)</small></span><br>
    </li>
    <br />
    <li>
        <span style="color: #2c2c2c;">Создать ссылку на storage:</span><br>
        <b style="color: #2c2c2c;">(sudo) docker-compose run php-fpm php artisan storage:link</b><br>
    </li>
</ul>