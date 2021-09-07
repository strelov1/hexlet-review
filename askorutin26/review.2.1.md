Добрый день. Артем! Отличная работа!


https://github.com/askorutin26/frontend-project-lvl2/blob/b977bce9efd00bf66e5d5a758daf8871b0a73164/bin/gendiff.js#L12

```
 `${program.opts().format}`
```

Здесь и так строка, не понятно зачем здесь интерполяция


---

https://github.com/askorutin26/frontend-project-lvl2/blob/b977bce9efd00bf66e5d5a758daf8871b0a73164/src/parsers.js#L5-L19

Функция пытается сделать слишком много, определяет тип файла, загружает его содержимое и парсит, нужно разделить ответственность этой функция, чтобы она только принимала содержимое и формат на выход возвращала распашенный объект


---

https://github.com/askorutin26/frontend-project-lvl2/tree/b977bce9efd00bf66e5d5a758daf8871b0a73164/src

Принято делать `index.js` файл как точку входа, где можно как просто экспортировать главную функцию, так и там ее объявлять

С именами файлов в этой директории есть проблемы:

makePath.js - читая такое имя файла ожидаешь, что в этом файле будет функция, создающая пути),
но там лежит функция нормализующая путь, вообще стоит подумать стоит ли такую функцию выделять в отдельный файл

parsers.js - Здесь лежит фабрика возвращающая один парсер а не множество

showDiff.js - читая такое имя файла ожидаешь, что в этом файле будет функция, отражающая дифф - но там происходит очень много всего, index.js - такое имя отлично бы подошло для данного файла


---

https://github.com/askorutin26/frontend-project-lvl2/blob/b977bce9efd00bf66e5d5a758daf8871b0a73164/src/buildDiffTree.js

Что-то слишком хорошо для первой попытки, признайся подглядел где-то?)

---

https://github.com/askorutin26/frontend-project-lvl2/blob/b977bce9efd00bf66e5d5a758daf8871b0a73164/src/formatters/plain.js#L21

${keys.join('.')} - можно сформировать 1 раз выше, сохранить в переменную и использовать где требуется

---

https://github.com/askorutin26/frontend-project-lvl2/blob/b977bce9efd00bf66e5d5a758daf8871b0a73164/src/formatters/stylish.js#L13

Этот отступ легко получить с помощью базового отступа, перемноженного на глубину (objIndentCount * indentLvl)

objIndentCount  - Подумай еще хорошенько над именем переменной

---

https://github.com/askorutin26/frontend-project-lvl2/blob/b977bce9efd00bf66e5d5a758daf8871b0a73164/src/formatters/stylish.js#L35-L39

У нас уже есть все для расчета отступов, зачем здесь стоят пробелы?
```
 `  ${indent}
```

Если мы захотим сменить заполнитель с пробела к примеру на * то нам придется слишком много менять в коде, если мы захотим изменить базовый отсуп это тоже помешает нам

---

https://github.com/askorutin26/frontend-project-lvl2/blob/b977bce9efd00bf66e5d5a758daf8871b0a73164/src/formatters/stylish.js#L3

Символ заполнитель стоит выделить в константу, а функция repeat выглядит спорно

---


https://github.com/askorutin26/frontend-project-lvl2/blob/b977bce9efd00bf66e5d5a758daf8871b0a73164/__tests__/gendiff.test.js


Можно уменьшить количество кода в тестах используя test.each. Ведь логика каждого теста одинакова и отличается только набором данных.

В таблице для each передать имена файлов, а в самих тестах уже получать содержимое файлов через expect

https://jestjs.io/docs/en/api#testeachtablename-fn-timeout

```
test.each([
  [1, 1, 2],
  [1, 2, 3],
  [2, 1, 3],
])('.add(%i, %i)', (a, b, expected) => {
  expect(a + b).toBe(expected);
});
```


---


Все вопросы, которые возникают, задавайте мне в слаке. Там мы их сможем оперативно решить.
