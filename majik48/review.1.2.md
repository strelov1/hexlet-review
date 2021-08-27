Евгений, День добрый!

Вы хорошо отрефакторили проект, код стал проще для понимания, но остались еще моменты которые можно сделать лучше.

---

https://github.com/majik48/frontend-project-lvl1/blob/master/bin/brain-calc.js#L3-L6

Назначение бинарного файла только запускать игру, он не должен знать не о движке не о игровых данных
Сюда импортируются именно игры, а сами игры и запускают движок

---

https://github.com/majik48/frontend-project-lvl1/blob/master/src/index.js#L28

Кроме самого движка, из этого модуля не требуется ничего экспортировать

---

https://github.com/majik48/frontend-project-lvl1/blob/master/src/index.js#L22

https://github.com/majik48/frontend-project-lvl1/blob/master/src/index.js#L25

Возвращать console.log не нужно, сам вызов ее возвращает всегда undefined, но лучше делать прерывание кода более явно

```
console.log(wrong);
return ;
```

---

https://github.com/majik48/frontend-project-lvl1/blob/master/src/index.js#L17

https://github.com/majik48/frontend-project-lvl1/blob/master/src/index.js#L18

Данный код не имеет смысла выделять в константы, код станет чище если эти строки будут определяться в месте вывода

```
console.log(`Correct!`);
```

---

https://github.com/majik48/frontend-project-lvl1/blob/master/src/index.js#L12

rules - не самое удачное имя для передачи содержимого, при чтении создается ощущение что в ней хранится массив каких-то игровых правил, хотя в ней хранится описание правил игры

---

https://github.com/majik48/frontend-project-lvl1/blob/master/src/games/brain-progression.js#L2

Для каждой игры эти константы должны определяться индивидуально, так изменяя правила в одной игры это распространяется на все


---

https://github.com/majik48/frontend-project-lvl1/blob/master/src/games/brain-progression.js#L8-L9

Эту функцию нужно сделать [чистой](https://ru.wikipedia.org/wiki/%D0%A7%D0%B8%D1%81%D1%82%D0%BE%D1%82%D0%B0_%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B8).

Все параметры для генерации подготовить заранее и передать в виде аргумента в функцию

---


https://github.com/majik48/frontend-project-lvl1/blob/master/src/games/brain-calc.js#L8-L11

Можно избавиться от мутации этой переменной если сразу возвращать результат через return

```
switch (operator) {
    case '+':
      return operand1 + operand2;
    case '-':
      return operand1 - operand2;
```


---

https://github.com/majik48/frontend-project-lvl1/blob/master/src/games/brain-calc.js#L20

default в свитчах необходимо обрабатывать по особому, подробнее можно почитать [здесь](https://ru.hexlet.io/blog/posts/sovershennyy-kod-defolty-v-svitchah)
