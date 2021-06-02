Супер! И еще немного правок для наведения лоска!


---

https://github.com/Estense/frontend-project-lvl1/blob/873d91e7d0eef22ac8eb6babeba3cc994d5ad4b4/src/games/brain-prime.js#L6-L16

https://github.com/Estense/frontend-project-lvl1/blob/873d91e7d0eef22ac8eb6babeba3cc994d5ad4b4/src/games/brain-even.js#L6-L11

Подстройка поведения функции под интерфейс, советую еще раз внимательнее ознакомиться со статьей https://ru.hexlet.io/blog/posts/sovershennyy-kod-proektirovanie-funktsiy


---


https://github.com/Estense/frontend-project-lvl1/blob/873d91e7d0eef22ac8eb6babeba3cc994d5ad4b4/src/games/brain-prime.js#L21

Возврат функции передается массив с двумя параметрами, первый преобразование правильного ответа в строку, второй какая-то цифра, лучше подготовить данные заранее и вернуть то что ожидает движок

https://github.com/Estense/frontend-project-lvl1/blob/873d91e7d0eef22ac8eb6babeba3cc994d5ad4b4/src/index.js#L10

```
const [rightAnswer, questionBody] = getData();
```

---

https://github.com/Estense/frontend-project-lvl1/blob/873d91e7d0eef22ac8eb6babeba3cc994d5ad4b4/src/cli.js#L3-L6

Есть ли смысл выносить эту операцию в отдельную функцию, делает ли это код проще для чтения, функции должны скрывать за собой какую-либо абстракцию, что скрывает данные функция?


---

https://github.com/Estense/frontend-project-lvl1/blob/873d91e7d0eef22ac8eb6babeba3cc994d5ad4b4/src/cli.js#L12

От этой функции никто не ожидает возврата, а также из-за этого функция стала нарушать принцип  [CQRS ](https://ru.wikipedia.org/wiki/CQRS)


---

https://github.com/Estense/frontend-project-lvl1/blob/873d91e7d0eef22ac8eb6babeba3cc994d5ad4b4/src/index.js#L5

Это не счетчик, такое название может сбить с толку так как обычно счетчик это мутируемая переменная в которой сохраняются значения текущией итерации, данная константа просто указвает на ограничение количество раундов


---

https://github.com/Estense/frontend-project-lvl1/blob/873d91e7d0eef22ac8eb6babeba3cc994d5ad4b4/src/games/brain-calc.js#L29-L30

В случае возврата default именовать функцию не обязательно, имя файла должно быть достаточным

```
export default () => generateGame(gameDescription, getData);
```

---
https://github.com/Estense/frontend-project-lvl1/blob/873d91e7d0eef22ac8eb6babeba3cc994d5ad4b4/src/games/brain-gcd.js#L11

Если нод уже нашли, можно прервать цикл с помощью return вернуть результат сразу