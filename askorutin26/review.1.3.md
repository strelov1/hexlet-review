Артем, день добрый!

Вы хорошо отрефакторили проект, логика значительно упростилась и кода стало ещё меньше, что очень хорошо. Продолжим работу над вашим проектом.

---

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/even-game.js#L7

Такие функции правилнее будет объявлять на уровне модуля там же где объявлена playBrainEven, так как при каждом вызове getQuestionAndAnswer, а он вызывается до 3 раз за игру, у нас происходит повторное определение функции перед ее использованием, иногда такое поведение необходимо но не в нашем случае

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/even-game.js#L5

---


https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/even-game.js#L11

rightAnswer отличное название, но вот с number совсем не то что ожидает движок


---

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/prime-game.js#L8

---

Из прочтения имени функции можно сделать вывод, что она возвращает предикат является ли число простым, на деле она делает совсем не это

---

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/prime-game.js#L10-L18

Не стоит эти две связанные операции разделять на две функции, лучше выделить отдельную функцию на уровне модуля isPrime - которая принимает число и возвращает булево значение


---

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/prime-game.js#L12

Алгоритм можно оптимизировать с помощью Math.sqrt(num), также когда мы уже знаем ответ, можно прерывать цикл и не продолжать счет дальше

---
https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/calc-game.js#L22

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/prime-game.js#L20

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/progression-game.js#L20

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/gcd-game.js#L25

Проблема с именованием см. выше, нужно передавать переменные которые ожидает движок

---

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/progression-game.js#L11-L19

Стоит выделить отдельно функцию, которая генерирует прогрессии в занном диапазоне и шагом, и также отделить функцию, которая скрывает искомый элемент (формирует вопрос)

---

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/gcd-game.js#L13-L24

Нужно разделить функцию формирующую ответ и функцию занимающуюся расчетом НОД на подобие как у нас выделена isEven 

---

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/gcd-game.js#L20

Можно прервать не только цикл, но и функцию с помощью return и сразу вернуть результат, это упростит чтение кода

---

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/gcd-game.js#L16

Не стоит экономить пространство и размещать блочные конструкции на одной строке

```
if (num1 < num2) {
    smallerNum = num1;
} else {
    smallerNum = num2;
}
```

---

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/index.js#L12

Функции всегда глаголы

---

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/index.js#L5

Эту константу следует выделить на уровне модуле, это позволит ее в будущем протестировать

---


https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/cli.js#L7

Функция нарушает принцип [CQRS ](https://ru.wikipedia.org/wiki/CQRS), тем-более в месте ее вызывающем от нее никто не ожидает како-го либо возврата


---

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/index.js#L7


На 5 шаге указано 

```
Файл cli.js не предназначен для описания логики игр.
Файлы, которые мы добавили ранее (src/cli.js, bin/brain-games.js), оставьте как есть и не смешивайте с остальным кодом.
```

---


https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/index.js#L6

Этот текст используется только во одном месте, нет никакого смысла его определять отдельно


---

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/README.md

В инструкции установки указано что при установки нужно ввести make link

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/Makefile

Но такой команды не существует

---

https://github.com/askorutin26/frontend-project-lvl1/tree/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games

В директории уже указано games, этого контекста достаточно чтобы понять что здесь хранятся игры, нет необходимости добавлять game в каждое имя файла

---

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/calc-game.js#L17-L22

Этот код с вычислениями нужно выделить в отдельную функцию, принимающую операцию и два операнда, и возвращающую расчитанный результат

---

https://github.com/askorutin26/frontend-project-lvl1/blob/7f1590bc7a5c11a238018644c7bb3a7d1197ccf7/src/games/calc-game.js#L12-L16

Аналогично с функцией формирующую вопрос