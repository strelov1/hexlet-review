Еще немного правок :-)

https://github.com/aleksandrchusovitin/frontend-project-lvl1/blob/b4f23ca51a666f095aa490be465d29a7b64ef8e2/README.md

```
# install the package
npm link
```

Эту команду можно также вынести в Makefile

---

https://github.com/aleksandrchusovitin/frontend-project-lvl1/blob/b4f23ca51a666f095aa490be465d29a7b64ef8e2/src/games/game-calc.js#L19-L20

Нужно добавить возврат исключений в дефолтное поведение, подробнее можно почитать здесь https://ru.hexlet.io/blog/posts/sovershennyy-kod-defolty-v-svitchah, сейчас если в функцию getCorrectAnswer передаеть неизвестный оператор, то функция вернет просто undefiend,
такой результат может привести к неожиданному поведению и часам отладки, на то чтобы это обнаружить

---

https://github.com/aleksandrchusovitin/frontend-project-lvl1/blob/b4f23ca51a666f095aa490be465d29a7b64ef8e2/src/games/game-calc.js#L22

Нужно стараться делать функции с единственной ответственностью, только подсчет результата преобразование форматов лучше вынести на верхний уровень

---

https://github.com/aleksandrchusovitin/frontend-project-lvl1/blob/b4f23ca51a666f095aa490be465d29a7b64ef8e2/src/games/game-calc.js#L7

Имя функции должно отражать суть процесса, подробнее о именовании https://ru.hexlet.io/blog/posts/naming-in-programming

Если перевести что делает это функция то получилось бы такое имя
calculateAndCastString - уже по названию видно что с функцией что-то не так и она делает слишком много

От подобных преобразований кода никуда не деться, но лучше выносить их на верхний уровень, иначе у нас каждая функция будет заниматься еще преобразование форматов

---

https://github.com/aleksandrchusovitin/frontend-project-lvl1/blob/b4f23ca51a666f095aa490be465d29a7b64ef8e2/src/games/game-calc.js#L8-L17

Можно избавиться от мутации этой переменной если сразу возвращать результат через return

```
switch (operator) {
    case '+':
      return operand1 + operand2;
    case '-':
      return operand1 - operand2;
```

---

https://github.com/aleksandrchusovitin/frontend-project-lvl1/blob/b4f23ca51a666f095aa490be465d29a7b64ef8e2/src/games/game-prime.js#L6-L14

Для отрицательных значений, а также для 0 и 1 функция возвращает неверное значение
https://en.wikipedia.org/wiki/Prime_number
