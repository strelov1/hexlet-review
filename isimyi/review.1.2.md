
https://github.com/isimyi/frontend-project-lvl1/blob/97a9c7981bea4fb85d52ac3465244f2f013f7c0b/README.md

В ридми используется демо бейдж от кодклимата. Нужно добавить свой.

https://github.com/isimyi/frontend-project-lvl1/blob/97a9c7981bea4fb85d52ac3465244f2f013f7c0b/src/index.js#L5-L11

---

Эта функция по факту выполняет и другие операции, кроме запроса имени пользователя, тем самым нарушает [CQRS](https://ru.wikipedia.org/wiki/CQRS).

И текущее имя функции не очень подходит. Вообще, стоит задать вопрос: а для чего здесь выделена часть игрового процесса?

---


https://github.com/isimyi/frontend-project-lvl1/blob/97a9c7981bea4fb85d52ac3465244f2f013f7c0b/src/index.js#L3

Множественное число по семантике подходит для набора элементов, списка.

А здесь количественное значение – roundsCount.
Подробнее о именовании (#Количество) https://ru.hexlet.io/blog/posts/naming-in-programming


---

https://github.com/isimyi/frontend-project-lvl1/blob/97a9c7981bea4fb85d52ac3465244f2f013f7c0b/src/index.js#L13

rules – схожая ситуация.
gameData – имя функции должно содержать глагол. Какую операцию она выполняет?

---

https://github.com/isimyi/frontend-project-lvl1/blob/97a9c7981bea4fb85d52ac3465244f2f013f7c0b/src/index.js#L25
Такие штуки удобно выводить с помощью двух console.log().

---

https://github.com/isimyi/frontend-project-lvl1/blob/97a9c7981bea4fb85d52ac3465244f2f013f7c0b/src/games/game-even.js#L9

Question: – это строка из игрового процесса. Сейчас, если нужно будет изменить, например, на Question --> придётся править код всех игр.

https://github.com/isimyi/frontend-project-lvl1/blob/97a9c7981bea4fb85d52ac3465244f2f013f7c0b/src/games/game-calc.js#L6-L11

Эти значения связаны друг с другом. Их нужно хранить в одной структуре.

---

https://github.com/isimyi/frontend-project-lvl1/blob/97a9c7981bea4fb85d52ac3465244f2f013f7c0b/src/games/game-calc.js#L14

А вот имя этой функции не соответствует тому, что она делает. Она возвращает 2 значения.

---

https://github.com/isimyi/frontend-project-lvl1/blob/97a9c7981bea4fb85d52ac3465244f2f013f7c0b/src/games/game-gcd.js#L8

set используется обычно для функций, которые устанавливают значения, например, в объект.

---

https://github.com/isimyi/frontend-project-lvl1/blob/97a9c7981bea4fb85d52ac3465244f2f013f7c0b/src/games/game-progression.js#L6

https://github.com/isimyi/frontend-project-lvl1/blob/97a9c7981bea4fb85d52ac3465244f2f013f7c0b/src/games/game-progression.js#L24

Будет хорошо сделать эти функций [чистыми](https://ru.wikipedia.org/wiki/%D0%A7%D0%B8%D1%81%D1%82%D0%BE%D1%82%D0%B0_%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B8).

---

https://github.com/isimyi/frontend-project-lvl1/blob/97a9c7981bea4fb85d52ac3465244f2f013f7c0b/src/games/game-progression.js#L26-L27

Венгерская нотация в именовании, стоит избегать ее

---

https://github.com/isimyi/frontend-project-lvl1/blob/97a9c7981bea4fb85d52ac3465244f2f013f7c0b/src/games/game-prime.js#L6

Можно более лаконично: isPrime()

---

https://github.com/isimyi/frontend-project-lvl1/tree/97a9c7981bea4fb85d52ac3465244f2f013f7c0b/src/games

Из имени игровых модулей можно убрать приставку game. Ведь все игры хранятся в директории games.