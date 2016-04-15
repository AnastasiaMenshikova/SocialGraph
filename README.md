Необходимо создать [Standalone-приложение](https://vk.com/dev/standalone) в VK для построения социального графа.
На вкладке **Настройки** нам пригодится **ID приложения** для получения **access_token**. 

Чтобы его получить необходимо [сформировать](https://vk.com/dev/auth_mobile) **url**:
```
https://oauth.vk.com/authorize?client_id=IDприложения&scope=friends,offline&redirect_uri=https://oauth.vk.com/blank.html&display=page&v=5.21&response_type=token
```

После успешной авторизации можно формировать запросы к [API](https://vk.com/dev/api_requests).

После этого редактируем файл **settings.py**, вставляя туда полученные **access_token** и **user_id**.

Далее переходим по ссылке **https://vk.com/editapp?id=IDприложения&section=functions** и создаем хранимую процедуру **getMutual**.
Копируем содержимое **execute_getMutual.js** в форму и сохраняем.

Для получения глубинного списка друзей (друзья-друзей и т.д.) проделываем те же самые действия с **execute_deepFriends.js**, назвав хранимую процедуру **deepFriends**.
