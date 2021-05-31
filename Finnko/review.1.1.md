Добрый день. Алексей! Хорошая работа!


Сейчас наступает не менее важная часть разработки - рефакторинг кода. Далее я отправлю список замечаний.
Ваша задача внимательно изучить их и внести исправления в свой код

---

https://github.com/Finnko/frontend-project-lvl1/blob/2a5e00f180a27dc62a6006e9543f4b7eae681d85/README.md

Ссылка на codeclimate ведет на тестовый репозиторий codeclimate

---
https://github.com/Finnko/frontend-project-lvl1/blob/2a5e00f180a27dc62a6006e9543f4b7eae681d85/package.json#L4

Это описание попадает в npm репозиторий, разработчикам наткнувшийся на новый пакет было бы приятно если бы из этого описания сразу можно было понять о чем проект

https://github.com/Finnko/frontend-project-lvl1/blob/2a5e00f180a27dc62a6006e9543f4b7eae681d85/package.json#L5

В первом проекте мы ничего не импортируем из проекта, эта инструкция лишняя

---

https://github.com/Finnko/frontend-project-lvl1/blob/2a5e00f180a27dc62a6006e9543f4b7eae681d85/Makefile#L8-L13

Можно упростить до `chmod +x bin/*`, но в целом эта инструкция лишняя, npm link делает сам

---

https://github.com/Finnko/frontend-project-lvl1/blob/2a5e00f180a27dc62a6006e9543f4b7eae681d85/src/cli.js#L10

Функция нарушает принцип [CQRS ](https://ru.wikipedia.org/wiki/CQRS), на 5 шаге https://ru.hexlet.io/projects/44/members/14943?step=5 сказанно

```
Файл cli.js не предназначен для описания логики игр.
Файлы, которые мы добавили ранее (src/cli.js, bin/brain-games.js), оставьте как есть и не смешивайте с остальным кодом.
```

---

https://github.com/Finnko/frontend-project-lvl1/blob/2a5e00f180a27dc62a6006e9543f4b7eae681d85/src/utils.js#L1

Ниже функция getRandomNumberInRange, полностью перекрывает, то что делает функция getRandomNumber

---

https://github.com/Finnko/frontend-project-lvl1/blob/2a5e00f180a27dc62a6006e9543f4b7eae681d85/src/utils.js#L7-L15

Данная функция не только сравнивает ответы но и выводит сообщения о корректности - это сразу вопрос к ее наименованию а также нарушение CQRS, такой код не имеет смысл выделять в отдельную функцию

---

https://github.com/Finnko/frontend-project-lvl1/blob/2a5e00f180a27dc62a6006e9543f4b7eae681d85/bin/brain-calc.js#L5-L9

Назначение бинарного файла только запускать игру, он не должен знать не о движке не о игровых данных
Сюда импортируются именно игры, а сами игры и запускают движок

---

https://github.com/Finnko/frontend-project-lvl1/blob/2a5e00f180a27dc62a6006e9543f4b7eae681d85/src/index.js#L12-L18

Решение интересное, но не гибкое, нам нужно добиться того чтобы движок ничего не знал о игре, чего бы не передавала ему сама игра, благодаря этому мы сможем разрабатывать одновременно сколько угодо игр при этом не трогая движок

---

https://github.com/Finnko/frontend-project-lvl1/blob/2a5e00f180a27dc62a6006e9543f4b7eae681d85/src/index.js#L41-L47

Можно прервать цикл с помощью return сразу, для этого не нужно делать отдельную переменную с флагом

---

https://github.com/Finnko/frontend-project-lvl1/blob/2a5e00f180a27dc62a6006e9543f4b7eae681d85/src/games/calc.js#L9-L20

А вот эту операцию хорошо бы вынести в отдельный файл


---

https://github.com/Finnko/frontend-project-lvl1/blob/2a5e00f180a27dc62a6006e9543f4b7eae681d85/src/games/progression.js#L7-L22


Можно сделать функцию генерации прогерсси [чистой](https://ru.wikipedia.org/wiki/%D0%A7%D0%B8%D1%81%D1%82%D0%BE%D1%82%D0%B0_%D1%84%D1%83%D0%BD%D0%BA%D1%86%D0%B8%D0%B8), если передавать настройки через аргумент


---

https://github.com/Finnko/frontend-project-lvl1/blob/2a5e00f180a27dc62a6006e9543f4b7eae681d85/src/games/progression.js#L13-L19

Цикл for в данном контексте подходит лучше

---

https://github.com/Finnko/frontend-project-lvl1/blob/2a5e00f180a27dc62a6006e9543f4b7eae681d85/src/games/progression.js#L29

Генерацию ответа из прогрессии стоит вынести в отдельную функцию или хотябы переменную, чтобы из имени переменной было ясно что происходит в этом куске кода


Все вопросы, которые возникают, задавайте мне в слаке. Там мы их сможем оперативно решить.
