Поздравляю с завершением проекта!

Остались еще несколько моментов для домашней работы:

_________________

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/utils.js#L27-L29

Здесь принципиально чтобы имена свойств оставались такими же как и в исходной структуре. Представь что json.parse будет переименовывать свойства.

_________________

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/render.js#L35

Мы точно знаем какая ошибка произошла, почему unknown?

_________________

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/app.js#L23

Для таких мест, где используется заглушка в виде пустой функции, можно использовать _.noop из лодаш

Таким образом мы обозначаем что намерено поставил сюда заглушку, а не просто забыл написать тело функции, и в целом выглядит более читаемо

_________________

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/app.js#L68

Здесь лучше бы подошла структура Set https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Set

_________________

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/app.js#L103
Здесь лучше  сразу передавать нужный массив строк для сравнения, то есть функция валидейт не закладывается на работу только с feed