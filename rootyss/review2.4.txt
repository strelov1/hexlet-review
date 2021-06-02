https://github.com/rootyss/frontend-project-lvl2/blob/4d151bf2d22baa1095cb09eabc35a832b40c5a7a/README.md

В инструкции установки не хватает линковки `npm link` 
Сейчас выполнив пункты из инструкции не используя этой команды не добиться работоспособности утилиты

Эту команду также неплохо бы добавить в Makefile

_________________

https://github.com/rootyss/frontend-project-lvl2/blob/4d151bf2d22baa1095cb09eabc35a832b40c5a7a/package.json#L5

Канонической точкой входа служит отдельный index.js внутри проекта, который просто импортирует нужную функцию из src

```
"main": "index.js"
```

_________________

https://github.com/rootyss/frontend-project-lvl2/blob/4d151bf2d22baa1095cb09eabc35a832b40c5a7a/src/getObjDifference.js#L3

Название с префиксом get - получить, не самое подходящее в данном контексте, 
так как данная функция не получает а строит новый объект - если точнее то
[абстрактное синтаксическое дерево](https://ru.wikipedia.org/wiki/%D0%90%D0%B1%D1%81%D1%82%D1%80%D0%B0%D0%BA%D1%82%D0%BD%D0%BE%D0%B5_%D1%81%D0%B8%D0%BD%D1%82%D0%B0%D0%BA%D1%81%D0%B8%D1%87%D0%B5%D1%81%D0%BA%D0%BE%D0%B5_%D0%B4%D0%B5%D1%80%D0%B5%D0%B2%D0%BE) 

название файла соответственно тоже нужно поменять

_________________


Чтобы упростить синтаксис вызова этой фабрики, можно сразу передать в нее содержимое для парсинга, и вызвать напрямую без этой функции

https://github.com/rootyss/frontend-project-lvl2/blob/4d151bf2d22baa1095cb09eabc35a832b40c5a7a/src/index.js#L6


```
return JSON.parse(content);
return yaml.load(content);
```


_________________

https://github.com/rootyss/frontend-project-lvl2/blob/4d151bf2d22baa1095cb09eabc35a832b40c5a7a/src/parser.js#L3

Префикс в названии этой функции тоже не подходящий, если сделать преобразование из замечания выше, то префикс вовсе не будует нужен


_________________

https://github.com/rootyss/frontend-project-lvl2/blob/4d151bf2d22baa1095cb09eabc35a832b40c5a7a/src/formatters/index.js#L5-L15

Все выше касательно функции парсинга также касается и этой функции

Также название не отражает суть, так как здесь не происходит рендеринга а происходит преобразование - одного формата - ast в формат для вывода - т.е. форматирование


_________________

https://github.com/rootyss/frontend-project-lvl2/blob/4d151bf2d22baa1095cb09eabc35a832b40c5a7a/src/parser.js#L5-L8

В парсере появилась специфика, завязанная на `.` в файловой системы, лучше вынести эту специфику на уровень вверх - и там уберать эту точку
это позволит использовать эту функцию в другом контексте ничего не зная о файловой системе

Также у yml файла, часто встречается полное его сокращение yaml - неплохо бы  и этот случай

_________________

`https://github.com/rootyss/frontend-project-lvl2/blob/4d151bf2d22baa1095cb09eabc35a832b40c5a7a/__tests__/index.test.js`

Тесты можно упростить, с помощью конструкции test.each

https://jestjs.io/docs/en/api#testeachtablename-fn-timeout

Подготовив таблицу в кейсами как в примерах
```
test.each([
  [1, 1, 2],
  [1, 2, 3],
  [2, 1, 3],
])('.add(%i, %i)', (a, b, expected) => {
  expect(a + b).toBe(expected);
});
```

_________________


https://github.com/rootyss/frontend-project-lvl2/blob/4d151bf2d22baa1095cb09eabc35a832b40c5a7a/src/formatters/plain.js#L30

Не хватает отладочной информации о типе который попал в ошибочный случай


_________________


https://github.com/rootyss/frontend-project-lvl2/blob/4d151bf2d22baa1095cb09eabc35a832b40c5a7a/src/formatters/plain.js#L19

Так как эти данные есть не в каждой ноде дерева, лучше извлечь их по месту использования

https://github.com/rootyss/frontend-project-lvl2/blob/4d151bf2d22baa1095cb09eabc35a832b40c5a7a/src/formatters/plain.js#L26

_________________

https://github.com/rootyss/frontend-project-lvl2/blob/4d151bf2d22baa1095cb09eabc35a832b40c5a7a/src/formatters/plain.js#L17

Еще один момент для улучшения, это собирать names не строками, а наращивать в массив при каждом рекурсивном вызове
а при использовании просто собирать массив в строку `join('.')`

_________________

https://github.com/rootyss/frontend-project-lvl2/blob/4d151bf2d22baa1095cb09eabc35a832b40c5a7a/src/formatters/stylish.js

Этот код тоже можно улучшить, у нас тут появилась завязка на магических числах
https://github.com/rootyss/frontend-project-lvl2/blob/4d151bf2d22baa1095cb09eabc35a832b40c5a7a/src/formatters/stylish.js#L9,L10

4, 8, 2 - от которой можно избавиться

Чтобы глубже разобрать в теме советую перед рефакторингом этой функции пройти следующие испытание -

https://ru.hexlet.io/challenges/js_trees_stringify
