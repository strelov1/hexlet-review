Алина, день добрый!

Вы хорошо отрефакторили проект, логика значительно упростилась и кода стало ещё меньше, что очень хорошо. Продолжим работу над вашим проектом.


https://github.com/alinarobertovna/frontend-project-lvl1/blob/cac3815f48480dfed14ca9fb121baed7cfe7cd30/src/games/progression.js#L21

https://github.com/alinarobertovna/frontend-project-lvl1/blob/cac3815f48480dfed14ca9fb121baed7cfe7cd30/src/games/progression.js#L23

Здесь нужно использовать нашу функцию generateRandomNumber 

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/cac3815f48480dfed14ca9fb121baed7cfe7cd30/src/index.js#L3

Саму функцию стоит выделить в отдельный файл, так как она не имеет ничего общего с движком,
обычно файл для подобных функций, которые не имеет доменного отношения к нашему коду, выделяют в файл с названием utils.js

Также в функции необходима возможность задавать диапазоны значений, к примеру для получения рандомной 
оператора 
https://github.com/alinarobertovna/frontend-project-lvl1/blob/cac3815f48480dfed14ca9fb121baed7cfe7cd30/src/games/calc.js#L20

Мы могли бы задать предел от 0 до operators.length чтобы получить число не больше и не меньше заданного предела

```generateRandomNumber(0, operators.length)```

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/cac3815f48480dfed14ca9fb121baed7cfe7cd30/src/index.js#L5-L10

Имя функции greeting, из чего можно подумать что она занимается приветсвием, но на самом деле она делает не только это, а также получает и передает имя пользователя, тем самым нарушает принцип [CQRS](https://ru.wikipedia.org/wiki/CQRS)

---


https://github.com/alinarobertovna/frontend-project-lvl1/blob/cac3815f48480dfed14ca9fb121baed7cfe7cd30/src/games/calc.js#L12-L13

Сейчас если передать в 

`calculateExpression(1, 2, '/')`

мы получим явно не то что хотели
default в свитчах необходимо обрабатывать по особому, подробнее можно почитать [здесь](https://ru.hexlet.io/blog/posts/sovershennyy-kod-defolty-v-svitchah)

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/cac3815f48480dfed14ca9fb121baed7cfe7cd30/src/games/progression.js#L7

Прогрессия ограничена всего 10 символами, нужно сделать игру интереснее и более непредсказуемой и сгенерировать рандомную длину прогрессии

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/cac3815f48480dfed14ca9fb121baed7cfe7cd30/src/games/progression.js#L25

Наименования переменной figure может сбить с толку, здесь хранится элемент прогрессии (item, element, etc)

Можно ли не изучив код понять чем отличаются newQuestion от question?, приставка new в имени переменной обычно признак что не было времени подумать над именем переменной

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/cac3815f48480dfed14ca9fb121baed7cfe7cd30/src/index.js#L16

Имя переменной task также никак не относится к тому что хранит эта переменная, нужно сделать так чтобы из имени переменной можно было примерно понять ее содержимая с минимальным погружением в код