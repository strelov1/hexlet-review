Андрей, день добрый!

Вы хорошо отрефакторили проект, логика значительно упростилась и кода стало ещё меньше, что очень хорошо. Продолжим работу над вашим проектом.

---

https://github.com/Estense/frontend-project-lvl1/blob/main/package.json#L29

Не используемая зависимость в проекте, ее стоит удалить

---

https://github.com/Estense/frontend-project-lvl1/blob/main/README.md

Не хватает пошаговой инструкции установки

---

https://github.com/Estense/frontend-project-lvl1/blob/main/src/cli.js#L3

Такое определение переменной сразу вызывает побочный эффект, нужно изолировать вызов readlineSync через функцию, чтобы эта функция срабатывала не сразу при импорте модуля, а при вызове функции

---

https://github.com/Estense/frontend-project-lvl1/blob/main/bin/brain-calc.js#L4

bin файлы должны отвечать только за запуск игры, за вывод должен отвечать движок, сейчас у нас код с выводом стал размазан по проекту, часть в движке часть в bin файле

---

https://github.com/Estense/frontend-project-lvl1/blob/main/bin/brain-games.js#L4

Также вывод только в файле cli.js

---

https://github.com/Estense/frontend-project-lvl1/blob/main/src/index.js#L11-L20

В текущем контексте цикл for будет лучше отражать суть процесса

---

https://github.com/Estense/frontend-project-lvl1/blob/main/src/index.js#L4

Здесь проблемы именованием, эта константа не является счетчиком, в ней содержится количество раундов а не игр

---

https://github.com/Estense/frontend-project-lvl1/blob/main/src/index.js#L12-L13

Тут можно упростить до

```
const [rightAnswer, randomNum] = getData();
```

randomNum - Тут ведь не всегда рандомное число, подумайте какое имя для этой переменной подойдет лучше


---

https://github.com/Estense/frontend-project-lvl1/blob/main/src/games/brain-calc.js#L8-L9

randomSymbol - не является случайным символом, это индекс случайного числа,
лучше спроектировать функцию так, чтобы в нее действительно передавался символ, и не приходилось оперировать индексами, также не нужно передвать туда массив с символами

---

https://github.com/Estense/frontend-project-lvl1/blob/main/src/games/brain-calc.js#L7-L21

Можно избавиться от мутации этой переменной если сразу возвращать результат через return

```
switch (operator) {
    case '+':
      return operand1 + operand2;
    case '-':
      return operand1 - operand2;
```


---

https://github.com/Estense/frontend-project-lvl1/blob/main/src/games/brain-calc.js#L32

Лучше это преобразование поднять на уровень выше к переменной записывающие верный результат

```
const rightAnswer = getRightAnswer(randomSymbol, num1, num2, symbols).toString();
```

---

https://github.com/Estense/frontend-project-lvl1/blob/main/src/games/brain-progression.js#L7-L8

Можно сделать функцию генерации прогерсси [чистой](https://ru.wikipedia.org/wiki/%D0%A7%D0%B8%D1%81%D1%82%D0%BE%D1%82%D0%B0_%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B8), если передавать настройки через аргумент

---

https://github.com/Estense/frontend-project-lvl1/blob/main/src/games/brain-progression.js#L22-L23

Эти преобразования также стоит изолировать в правильную функцию, так чтобы из названия был ясен процесс происходящий в ней

---

https://github.com/Estense/frontend-project-lvl1/blob/main/src/games/brain-progression.js#L23

Это никак не рандомное число, это даже не число


---

https://github.com/Estense/frontend-project-lvl1/blob/main/src/games/brain-even.js#L6-L10

Нужно выделить определение четности в отдельную функцию
https://ru.hexlet.io/blog/posts/sovershennyy-kod-proektirovanie-funktsiy
в статье хороший пример как это делается

---


https://github.com/Estense/frontend-project-lvl1/blob/main/src/games/brain-prime.js#L7-L15

Также в отдельную функцию

---

https://github.com/Estense/frontend-project-lvl1/blob/main/src/games/brain-prime.js#L11

Алгоритм можно оптимизировать с помощью Math.sqrt(num);