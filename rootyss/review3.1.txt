Отличная работа! Знаю проект не из легких - вы хорошо потрудились!

https://github.com/rootyss/frontend-project-lvl3/blob/72cb884a9df982e9db1675ad4a494fccabbf1fcd/README.md

Не хватает инструкций по установке сборке и тестировании проекта

_________________


https://github.com/rootyss/frontend-project-lvl3/blob/72cb884a9df982e9db1675ad4a494fccabbf1fcd/Makefile#L15-L16

В текущем проекте ничего линковать не нужно

_________________

https://github.com/rootyss/frontend-project-lvl3/blob/72cb884a9df982e9db1675ad4a494fccabbf1fcd/Makefile#L9-L12

Обычно для поддержки обоих систем применяют cross-env

https://github.com/kentcdodds/cross-env#usage

https://jestjs.io/docs/ecmascript-modules

_________________


https://github.com/rootyss/frontend-project-lvl3/blob/72cb884a9df982e9db1675ad4a494fccabbf1fcd/src/app.js#L120

https://github.com/rootyss/frontend-project-lvl3/blob/72cb884a9df982e9db1675ad4a494fccabbf1fcd/src/app.js#L98-L103

У нас на входе только один инпут, по этому не нужно определять здесь валидацию схемы объекта

```.object().shape({```

Это лишнее

Также на входе, имеет смысл очищать от лишних пробелов по краям,
пользователи часто при копировании, захватывают область рядом,
из-за чего у них могут возникнуть не очевидные им проблемы с валидацией

_________________

https://github.com/rootyss/frontend-project-lvl3/blob/72cb884a9df982e9db1675ad4a494fccabbf1fcd/src/app.js#L18

Здесь поиск идет по всем постам, нужно ограничить выборку по источнику данных

Новые данные не подгружаются, этот [RSS](http://lorem-rss.herokuapp.com/feed)
обновляет посты каждую минуту


_________________

https://github.com/rootyss/frontend-project-lvl3/blob/72cb884a9df982e9db1675ad4a494fccabbf1fcd/src/app.js#L19

https://github.com/rootyss/frontend-project-lvl3/blob/72cb884a9df982e9db1675ad4a494fccabbf1fcd/src/app.js#L32

В эталоне добавления происходит в начале списка

_________________

https://github.com/rootyss/frontend-project-lvl3/blob/72cb884a9df982e9db1675ad4a494fccabbf1fcd/src/app.js#L140-L141

Обновление нужно запускать только после загрузки, 
из-за проблем с соединением или из-за загрузки большого количества постов, 
приложение со временем будет только и заниматься что сканированием rss

Протестировать такое поведение
можно например включив тротлинг сети https://css-tricks.com/throttling-the-network/

_________________

https://github.com/rootyss/frontend-project-lvl3/blob/72cb884a9df982e9db1675ad4a494fccabbf1fcd/src/locale/ru.js

Есть только перевод на русский, если переключить локаль на en
то мы увидим часть русского текста, и часть литералов на английском например
`errors.doubleUrl`

_________________

https://github.com/rootyss/frontend-project-lvl3/blob/72cb884a9df982e9db1675ad4a494fccabbf1fcd/src/app.js#L41

axios добавляет к ошибке свойство isAxiosError, корректнее определять по этому свойству

_________________

https://github.com/rootyss/frontend-project-lvl3/blob/72cb884a9df982e9db1675ad4a494fccabbf1fcd/src/app.js#L41-L47

Лучше бы смотрелось если этот код изолировать отдельную функцию

_________________


Разработка сильно бы упростилась если бы в проекте была использована горячая перезагрузка

https://webpack.js.org/guides/development/#choosing-a-development-tool

https://github.com/webpack/webpack-dev-server


