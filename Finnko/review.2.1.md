Добрый день. Алексей! Отличная работа!


https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/package.json#L4

Не хватает описания (description) - описание попадает в npm репозиторий, разработчикам наткнувшийся на новый пакет было бы приятно если бы из этого описания сразу можно было понять о чем проект


---

https://github.com/Finnko/frontend-project-lvl2/tree/906f23b564c92dae8997e4cf0c3d9557f7439265/.github/workflows

coverage.yml и tests-check.yml Можно было объеденить в один пайплайн, так у нас получилось что 2 раза происходит установка проекта

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/.github/workflows/coverage.yml#L17

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/.github/workflows/tests-check.yml#L16

И два раза запускаются тесты:

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/.github/workflows/tests-check.yml#L20

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/.github/workflows/coverage.yml#L24



---


https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/index.js#L9-L13

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/index.js#L72-L73

Парсер следует вынести в отдельную функцию фабрику (лучше еще в отдельный файл), которая принимает содержимое файла и формат, а на выходе возращает распаршенный объект


---

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/index.js#L16

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/index.js#L24

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/index.js#L40

Непонятно назначение интерполяции строк в этих местах `${key}`


---

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/index.js#L40

Это условие лишнее, предыдущие условия исключают возможность попадания в это условие

---

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/index.js#L41

Под условие isObject могут попасть также массивы, для этого лучше подходит isPlainObject


---

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/index.js#L49

Даже если объекты будут одинаковые, данная проверка всегда будет возвращать true. Сравнение корректней будет производить с помощью функции isEqual в lodash

---

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/index.js#L70

Определение формата, лучше изолировать в функцию

---

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/formatters/index.js#L13

default в свитчах необходимо обрабатывать по особому, подробнее можно почитать [здесь](https://ru.hexlet.io/blog/posts/sovershennyy-kod-defolty-v-svitchah)


https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/formatters/plain.js#L5-L7

---

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/formatters/plain.js#L5

_.isString

Старайся избегать однострочных условий это может, после if всегда стоит открывать фигурные скобки и переносить строку

---

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/formatters/plain.js#L13

Здесь проще было бы 
`[...path, key].join('.')`


---

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/formatters/stylish.js#L14

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/formatters/stylish.js#L36

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/formatters/stylish.js#L42

У нас вроде уже есть записанная константа SPACE_COUNT, но повсюду используется магические числа https://ru.hexlet.io/blog/posts/magic-numbers


---

https://github.com/Finnko/frontend-project-lvl2/blob/906f23b564c92dae8997e4cf0c3d9557f7439265/src/formatters/stylish.js#L42

Тут мы можем вернуть массив, если итерировать будем не с помощью map а flatMap
```
return [
    `${getIndent(indentValue - 2)}- ${key}: ${stringifyValue(node.oldValue, indentValue)}`,
    `${getIndent(indentValue - 2)}+ ${key}: ${stringifyValue(node.newValue, indentValue)}`
];
```

А переносы строк `\n` лучше вынести как разделитель при join
```
styledDiff.join('\n')
```


---

Все вопросы, которые возникают, задавайте мне в слаке. Там мы их сможем оперативно решить.
