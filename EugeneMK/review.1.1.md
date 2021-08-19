Добрый день. Евгений! Хорошая работа!

Сейчас наступает не менее важная часть разработки - рефакторинг кода. Далее я отправлю список замечаний.
Ваша задача внимательно изучить их и внести исправления в свой код

---

https://github.com/EugeneMK/frontend-project-lvl1/runs/3367259583?check_suite_focus=true

В первую очередь нужно добиться прохождения автоматических тестов

---

https://github.com/EugeneMK/frontend-project-lvl1/blob/4eadf0c27cdc7b33c645a4b2809ae8e424cc18c3/.gitignore

При такой записи будут игнорироваться как файлы с именем node_modules, так и директории с таким же именем. У нас задача игнорировать директорию node_modules в корне проекта.

Изучите таблицу паттернов по .gitignore и внесите необходимые изменения https://www.atlassian.com/git/tutorials/saving-changes/gitignore


---

https://github.com/EugeneMK/frontend-project-lvl1/tree/4eadf0c27cdc7b33c645a4b2809ae8e424cc18c3/games

Директория src должна содержать исходный код программы,
Игры также являются исходным кодом

---

https://github.com/EugeneMK/frontend-project-lvl1/blob/4eadf0c27cdc7b33c645a4b2809ae8e424cc18c3/README.md


В README можно включить инструкцию установки в текстовом формате, чтобы была возможность установить скопировав команды

---

https://github.com/EugeneMK/frontend-project-lvl1/blob/4eadf0c27cdc7b33c645a4b2809ae8e424cc18c3/src/cli.js#L3-L8

Имя функции greeting, из чего можно подумать что она занимается приветсвием, но на самом деле она делает не только это, а также получает и передает имя пользователя, тем самым нарушает принцип [CQRS](https://ru.wikipedia.org/wiki/CQRS)


---

https://github.com/EugeneMK/frontend-project-lvl1/blob/4eadf0c27cdc7b33c645a4b2809ae8e424cc18c3/src/index.js#L1


На 5 шаге указано 

```
Файл cli.js не предназначен для описания логики игр.
Файлы, которые мы добавили ранее (src/cli.js, bin/brain-games.js), оставьте как есть и не смешивайте с остальным кодом.
```

Все вопросы, которые возникают, задавайте мне в слаке. Там мы их сможем оперативно решить.
