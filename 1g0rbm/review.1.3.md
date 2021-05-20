Поздравляю с успешным завершением проекта!

---

Небольшое домашнее задание:

https://github.com/1g0rbm/frontend-project-lvl1/blob/fe65162df3e47fcfb4ccb8bf5c6d1dd300db74e0/src/index.js#L29-L30

Можно перенести это в терминальное условие в gameCycle. Если нужно, то можно завершить программу (return), если нет, то поздравить пользователя уже за пределами рекурсивной функции.

gameCycle, gameStep – имя функции должно содержать глагол и точно отражать ту операцию, которая реализована с помощью этой функции.

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/fe65162df3e47fcfb4ccb8bf5c6d1dd300db74e0/src/games/brain-even.js#L6

Всё же isEven :-)

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/fe65162df3e47fcfb4ccb8bf5c6d1dd300db74e0/src/games/brain-calc.js#L6-L10

Можно сделать еще круче, с помощью словаря

```
{ OPERATION_ADD: '+', ... }
```

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/fe65162df3e47fcfb4ccb8bf5c6d1dd300db74e0/src/games/brain-gcd.js#L22

Сейчас функция возвращает пару значений неявного назначения. Чтобы понять, что это, придётся анализировать код. Выделите под основные сущности отдельные константы. Так код станет более читаемым.

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/fe65162df3e47fcfb4ccb8bf5c6d1dd300db74e0/src/games/brain-prime.js#L12-L16

Нет необходимости проверять все делители. Если найдётся один, значит число не простое – можно возвращать результат.

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/fe65162df3e47fcfb4ccb8bf5c6d1dd300db74e0/src/games/brain-prime.js#L24

questionNumber – венгерская нотация. Её лучше избегать.
