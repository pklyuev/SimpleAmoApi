# SimpleAmoApi
Simple PHP AmoCRM API Library

Простая PHP библиотека для работы с API AmoCRM, которая работает с OAuth 2.0, без использования Api-key (устаревший метод).
В даной библиотеке отсутствуют дополнительные PHP-библиотеки (никакого композера и триллиона доп. библиотек, для извращенцев, которые, как и я, любят минимализм, где это возможно).
Библиотека сырая и будет дополнятся примерами + функциями, делается под свои задачи, может пригодится и вам.

Документация AmoCRM: https://www.amocrm.com/developers/content/api/account/
Как получить стартовые ключи: https://www.amocrm.ru/developers/content/oauth/step-by-step

По сути, нужно создать интеграцию в админке АМО, как указано в примере по ссылке выше и получить 3 сущности: client_secret (секретный ключ), client_id (ID интеграции), code (Код авторизации)

ВАЖНО: Код авторизации действителен всего 20 минут, что бы запустить скрипт в нормальную работу, нужно в течение этого времени в файле SimpleAmoApi.php внести в переменную $auth нужные данные + 
удалить файл auth.json, если он есть в каталоге AmoCRM (это нужно для генерации новых ключей OAuth).

Первый запуск нужно сделать сразу, что бы сгенерировались нужные ключи и сохранились в файл, тогда не нужно будет каждые 20 минут менять ключи, новый Access Token будет генерироваться сам при каждом запуске.

В качестве первого запуска скрипта, рекомендую делать тест на получение данных аккаунта, пример в example.php

Если вы увидите данные аккаунта (огромный массив с инфой по вашему кабинету), то все ОК, выдохните, вы молодец :)
Елси же будут какие-то ошибки или вы нарушили какие-то последовательности, то просто сгенерируйте в админке АМО в вашей интеграции новые ключи, внесите повторно в файл и запустите скрипт.

Автор: Мазур Павел (Colin990) Сайт: https://colin990.com/ С вопросами можно обращаться по контактам на сайте.
