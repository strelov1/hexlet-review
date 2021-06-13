Добрый день. Дмитрий! У вас получилось написать собственное приложение. Это очень хорошо.

Сейчас наступает не менее важная часть разработки - рефакторинг кода. Далее я отправлю список замечаний.
Ваша задача внимательно изучить их и внести исправления в свой код

---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/README.md

На странице должны отображаться сами аскинемы, а не ссылки на них. Так проект будет выглядеть более привлекательно для потенциальных работодателей, которые будут просматривать ваш репозиторий. Просмотрите как можно встроить на страницу аскинему https://asciinema.org/docs/embedding


Ссылка на codeclimate ведет на тестовый репозиторий codeclimate

---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/bin/brain-calc.js#L4

Имя функции всегда глагол, такое имя должно отражать суть процесса, подробнее о именовании https://ru.hexlet.io/blog/posts/naming-in-programming

---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/src/games/brain-calc.js#L11-L26

Можно избавиться от мутации этой переменной если сразу возвращать результат через return

```
switch (operator) {
    case '+':
      return operand1 + operand2;
    case '-':
      return operand1 - operand2;
```


---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/src/games/brain-calc.js#L23

Отлично, но для упрощения будущей отладки неплохо бы в ошибки сразу вернуть что за неизвестный оператор туда пришел

`Неизвестный оператор: ${operator}`

На всякий случай статейка на эту тему https://ru.hexlet.io/blog/posts/sovershennyy-kod-defolty-v-svitchah

---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/src/games/brain-calc.js#L36

В этом месте лучше не экономить на переменных и положить вопрос сначала в переменную, и ее уже передать, как сделано с correctAnswer 


---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/src/games/brain-calc.js#L6

У нас ведь уже есть `getRandomInt`, мы можем получить рандомные оператор через него, правильно указав диапазон значений

---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/src/games/brain-calc.js#L39-L41

Здесь можно вернуть сразу 

```
export default () => game('What is the result of the expression?', getGameData);
```

Функции всегда глаголы ```game```

---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/src/games/brain-even.js#L3

На деле такие комментарии избыточны, советую прочесть главу Самодокументирующийся код

https://www.notion.so/hexlet/092b8fff35104474b28021fabb05a0e2?v=40a4ece4f2074aa0b9c3e232359a85ce&p=51ecb84532be4319b302c0faf041f7ab

---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/src/games/brain-gcd.js#L17

Экономия на переменных здесь, ухудшает читабельность кода

---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/src/games/brain-progression.js#L13-L22

Чтобы улучшить читабельность кода здесь, советую выделить в отдельные функции создание прогрессии по заданным параметрам, и скырите элемента прогрессии

---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/src/index.js#L12

Есть ли смысл выделять такой код в отдельную функции?
Таким образом мы создаем лишнюю абстракцию, которая скрывает за собой только вызов console.log,

---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/src/index.js#L4-L9

Эта функция выполняет две операции, приветствие и получение имени, тем самым нарушает [CQRS](https://ru.wikipedia.org/wiki/CQRS).

---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/src/index.js#L18

Лучше поднять эту константу на уровне модуля. При необходимости её можно будет экспортировать из модуля и использовать там где это нужно. Также это позволит протестировать её значение

---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/src/index.js#L17


Старайтесь делать имена переменных, которые могли бы описать содержимое в этой переменной, при минимальном контексте. Переменная с именем `text` говорит какого типа содержимое, но совсем непонятно для чего этот текст нужен

---

https://github.com/oddzye/frontend-project-lvl1/blob/a79b902a91142f82a3d87874cced0e6d803652b2/src/index.js#L36-L40

Данная функция не имеет отношения к движку, эта функция общего назначения и ее следует поместить в отдельный файл и оттуда ее экспортировать, обычно такой файл называют что-то вроде utils.js

---

Все вопросы, которые возникают, задавайте мне в слаке. Там мы их сможем оперативно решить.
