Просмотр данной страницы с доп оформлением доступен здесь: ![Click me](https://xeval-project.github.io/RichPresence/)

----



# RichPresence
RichPresence with Assets, timestamps, party, state, details...

# LICENSE
Данный репозиторий выложен под лицезнией `MIT`, не стесняйтесь брать из него части кода или форкать его, если вы думаете что можете помочь улучшить данный гит, то отправляйте нам `PULL REQUEST'S`, мы расмотрим их, так-же вы можете работать с нами в нашей организации.
# Установка
## Загрузка файлов
Для начала вы должны форкнуть либо скачать данный репозиторий на свое устройство.

Код (для док сайта)

```js
//Версия 0.2.1
const Discord = require('discord.js');
const client = new Discord.Client();

let token = "" //вставьте токен сюда.

client.on('ready', () => {
  console.log("Ожидание установки статуса...");
client.user.setPresence({
  status: 'online', //статус вашего аккаунта (dnd, idle, invisible, online)
game: {
        name: 'Cosmoteer', //название вашей игры
        state: 'В игре', //текст на 2 линии
        details: 'Играет за корабль Dest-fall', //текст на 1 линии
   type: 'PLAYING', //новое. Не обязательно. От Qadik а. Типы: 'PLAYING' - играет, 'STREAMING' - стримит, 'LISTENING' - слушает и 'WATCHING' - смотрит.
      //url: "", //В основном не нужно. Сюда надо указывать ссылку на стрим в твиче 
  application_id: '442351930929577995', //приложение в котором содержатся все ассесты
        spectateSecret: 'look', //секрет для наблюдения
assets: { 
          small_image: '465138149413224483', //id от маленько ассеста
          small_text: 'X-49.', //текст который будет виден при наведение на маленький ассест
          large_image: '465138072498208768', //id от большого ассеста
          large_text: 'Cosmoteer.' //текст который будет виден при наведение на большой ассест
        },
        timestamps: { //метки времени
          start: Date.now() // устанавливает дату запуска как метку для timestamp (то есть время начнется с [прошло 00:00])
        }, // поменяйте на end и замените Date.now() если хотите произвольную дату, указывать нужно в unix => https://www.unixtimestamp.com/
        party: {
        id: 'ae488379-351d-4a4f-ad32-2b9b01c91657', // ид пати
        size: [8,8] //размер виртуального пати, вы можете хоть его переполнить
        },
        secrets: { //это секреты для пати, вход и просмотр игры, однако я так и не смог их настроить...
        match: 'xyzzy', //матч
        join: 'join', //секрет входа
        spectate: 'look' // секрет наблюдения
        }
      }
});
console.log("Успешно! Создатели: Группа XeVAL PROJECT");
});
if(token) {
client.login(token).catch(e=> console.log(e))
} else {
client.login(process.env.TOKEN)
}
```
## Первый этап
* Для установки в Windows и MacOS X заходим на сайт https://nodejs.org и скачиваем последню весию (последнюю не обязательно, но желательно. Также лучше новичкам устанавливать LTS версию)

* Для установки в Linux нам надо добавить репозиторий.

Для этого заходим в терминал и пишем:

```$ sudo apt-add-repository ppa:chris-lea/node.js```

Если не получилось и написало ошибку, тогда пишем вместо этой команды эту:

```$ sudo add-apt-repository ppa:chris-lea/node.js```

Далее пишем:

```$ sudo apt update```

Теперь пишем команду:

```$ sudo apt-get install nodejs```

Готово!

## Второй этап
Второй этап установки уже ничем не отличается от установленной ОС, будь это Windows, MacOs X или Linux, кроме некоторых моментов.
Отправляемся в командную строку, есть 2 варианта:

1 вариант:

В Linux жмём правой кнопкой мышки в любое свободное пространство файлового менеджера (при этом вы должны находиться в директории со скриптом + не все файловые менеджеры оснащены этим функционалом) и жмёте `открыть в терминале`.

В Windows также, но с зажатой клавишей Shiht и там функция называется `Открыть в командной строке`.

В MacOS X скоро будет...

2 вариант:

В Linux е и Windows заходим в командную строку и пишем:

```$ cd ваша_директория/```

В MacOS X тоже пока неизвестно...

Теперь пишем:

```$ npm i discord.js```

Готово!

# Запуск

В командной строке пишем:

```$ node .```
