
Добрый день. Александр! Очень хорошая работа, приятно было проверять! 

Теперь самое время сделать работу еще лучше :)

---

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8df188f7df2e371bb1a4ac529c5b2ebc6fa068ce/src/parsers.js#L5-L8

Парсер ничего не должен знать о файловой системе, точка в расширении это часть файловой системы


---

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8df188f7df2e371bb1a4ac529c5b2ebc6fa068ce/src/buildTree.js#L19

Под условие isObject могут попасть также массивы, для этого лучше подходит isPlainObject

---

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8df188f7df2e371bb1a4ac529c5b2ebc6fa068ce/src/buildTree.js#L23

Даже если объекты будут одинаковы, данная проверка всегда будет возвращать true. Сравнение корректней будет производить с помощью функции isEqual в lodash

---

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8df188f7df2e371bb1a4ac529c5b2ebc6fa068ce/src/formatters/formatPlain.js#L16

Статус все же не очень подходящие именование переменной, что эта переменная отражает?

---

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8df188f7df2e371bb1a4ac529c5b2ebc6fa068ce/src/formatters/formatPlain.js#L15

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8df188f7df2e371bb1a4ac529c5b2ebc6fa068ce/src/formatters/formatPlain.js#L26

Тут немножко запутано получилось, не поятно для чего flat, join можно сделать 1 раз чтобы не делать его в 4 месах, а также в реркусивный вызов лучше передавать именно массив а не строку, так как при выводе она все равно джоинется

---

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8df188f7df2e371bb1a4ac529c5b2ebc6fa068ce/src/formatters/formatPlain.js#L23-L24

Тут правильнее было бы возвращать null а не unchanged node, а еще лучше было бы отфильтровать сам тип unchanged выше перед map

---

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8df188f7df2e371bb1a4ac529c5b2ebc6fa068ce/src/formatters/formatPlain.js#L32

Не понятно для чего здесь создается новый массив, почему сразу не `.join('\n')`

---

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8df188f7df2e371bb1a4ac529c5b2ebc6fa068ce/src/formatters/formatStylish.js#L1

В данном случае отступ не получается а создается - make, create лучше подходит в данном контексте

---
https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8df188f7df2e371bb1a4ac529c5b2ebc6fa068ce/src/formatters/formatStylish.js#L11

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8df188f7df2e371bb1a4ac529c5b2ebc6fa068ce/src/formatters/formatStylish.js#L13

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8df188f7df2e371bb1a4ac529c5b2ebc6fa068ce/src/formatters/formatStylish.js#L31

Очень много магических чисел, подробнее о них https://ru.hexlet.io/blog/posts/magic-numbers
Некоторые можно поместить в константу, а от остальных вполне можно избавиться

