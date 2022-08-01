<div align="center">
 <h1 align="center">  Discord bot </h1>
 <strong>Шаблон дискорд бота на языке Python и на библиотеке Disnake</strong><br />Для корректной работы бота советую установить Python 3.9 и выше<br /><br/>
 </div>
 
## Начало работы
### Установка Python
1. Тыкаем [сюда](https://www.python.org/ftp/python/3.9.0/python-3.9.0-amd64.exe) и у вас скачивается Python 3.9

2. **Обязательно** включаем галочку рядом с *Add Python 3.9 to PATH* и проходим дальнейшую установку

После установки Python вы так же можете установить **Visual Studio Code** для редактирования файлов бота по этой [ссылке](https://code.visualstudio.com/Download)

### Работа с ботом
#### Создание нового бота на сайте [Discord Developers Portal](https://discord.com/developers/applications)

1. Заходим на [сайт](https://discord.com/developers/applications) и нажимаем на кнопку **New Application**
2. Вводим название приложения и нажимаем **Create**
3. Выбираем вкладку **Bot**
4. Нажимаем **Add Bot**
5. И снова нажимаем **Yes, do it!**
6. Нажимаем **Reset Token** и сохраняем его где-нибудь

#### Настройка интентов (для слеш команд)

Во вкладке **Bot** включаем следующие галочки
1. Public Bot (не обязательно)
2. Presence Intent
3. Server Members Intent
4. Message Content Intent

#### Корневой файл **bot.py**
##### 1. Персонализация бота
###### Статусы
 Онлайн
 ```py
status=disnake.Status.online
```

 Оффлайн
 ```py
status=disnake.Status.offline
```

 Не беспокоить
 ```py
status=disnake.Status.dnd
```

 Не активен
```py
status=disnake.Status.idle
```

###### Активности
 Играет в
 ```py
 activity=disnake.Game(name="игру")
 ```
 
 Смотрит
 ```py
 activity=disnake.Activity(type=disnake.ActivityType.watching, name="ютуб")
 ```
 
 Слушает
 ```py
 activity=disnake.Activity(type=disnake.ActivityType.listening, name="музыку")
 ```
 
 Стримит
 ```py
 activity=disnake.Streaming(name="стрим", url="https://www.twitch.tv/никнейм") #если убрать аргумент url то кнопки просто не будет, но все будет работать
 ```
 
 Соревнуется в
 ```py
 activity=disnake.Activity(type=disnake.ActivityType.competing, name="игре")
 ```

###### Test Guilds
 Этот термин обозначает принудительное включение слеш команд на определённых серверах
 
 Что бы добавить туда свой сервер напишите так
 ```py
 test_guilds=[960169222808432660]
 ```
 
 Что бы добавить несколько серверов напишите так
 ```py
 test_guilds=[960169222808432660, 941767647790514216]
 ```
 **Важно** - Если айди вашего сервера не будет там то слеш команда появится/обновится только через час после её добавления/изменения
 
 ### Термины
 #### Ког - модуль бота где хранятся команды, можно создать несколько когов (Модерация, Развлечение и.т.п)
 #### Токен - код с помощью которого код с ботом подключается к дискорду
