Добрый день. Алина! Отличная работа!

Сейчас наступает не менее важная часть разработки - рефакторинг кода. Далее я отправлю список замечаний.
Ваша задача внимательно изучить их и внести исправления в свой код

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/package.json#L5

Это описание попадает в npm репозиторий, разработчикам наткнувшийся на новый пакет было бы приятно если бы из этого описания сразу можно было понять о чем проект

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/package.json#L6

В первом проекте мы ничего не импортируем из проекта, эта инструкция лишняя

---

Также в README можно включить инструкцию установки в текстовом формате, чтобы была возможность установить скопировав команды

Ссылка на codeclimate ведет на тестовый репозиторий codeclimate

---

https://github.com/alinarobertovna/frontend-project-lvl1/tree/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/games

Директория games является часть исходного кода и должна находится в директории src

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/bin/brain-even.js#L5

Функции это всегда глаголы, подобробнее о хорошем наименование можно почитать [здесь](https://ru.hexlet.io/blog/posts/naming-errors-1)

Хорошее наименование функции, отражает суть процесса запускающегося в функции

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/src/index.js#L24

Данный ход у нас терминальный, с помощью return мы можем прерывать не только цикл, но и саму функцию

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/src/index.js#L26-L28

Эту проверку можно убрать, если вынести этот вывод за пределы цикла, при условии что терминальное условие выйдет из функции см. выше

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/src/index.js#L12

Старайтесь делать имена переменных, которые могли бы описать содержимое в этой переменной, при минимальном контексте. У нас тут появилось новое понятие задачи, без изучения кода, будет сложно понять что в ней храниться

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/games/calc.js#L7-L19

Можно избавиться от мутации этой переменной если сразу возвращать результат через return

```
switch (operator) {
    case '+':
      return operand1 + operand2;
    case '-':
      return operand1 - operand2;
```

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/games/calc.js#L35-L38

Здесь можно сразу возвращать вызов анонимной функции

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/games/calc.js#L36

функции глаголы см. выше :-) Советую пройтись по всем функциям в проекте, и посмотреть удовлетворяют ли они всем требованиям хорошего наименования

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/games/calc.js#L24

Генерацию рандомных чисел стоит выделить в отдельную функцию, тем более она используется не в одной игре, таким образом ее можно будет переиспользовать

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/games/calc.js#L31-L32

В данном случае можно было обойтись без переменной и возвращать сразу массив

`return [question, correctAnswer]`

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/games/even-game.js#L8-L13

Стоит выделить функцию определения четности в отдельную функцию

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/games/progression.js#L7-L8

Функцию генерацию прогрессии лучше сделать чистой, а параметры ее генерации передать в виде аргументов извне.

Это же относится к функции скрывающий элемент

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/games/progression.js#L15-L20

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/games/progression.js#L22-L39

Тут очень сложный подход, гораздо проще будет идти таким порядком

1. сгенерировать прогрессию
2. извлечь рандомные элемент прогрессии - он же станет у нас correctAnswer
3. скрыть полученный на втором шаге элемент прогрессии

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/ef68c0939f1b4157e4cb7239adcb90faf13a2ffe/games/prime.js#L5-L19

Здесь есть проблемы с разделением уровней абстракции, советую ознакомиться с этой статей, в ней разбирается похожий пример
https://ru.hexlet.io/blog/posts/sovershennyy-kod-proektirovanie-funktsiy

---

Все вопросы, которые возникают, задавайте мне в слаке. Там мы их сможем оперативно решить.
