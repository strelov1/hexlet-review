Добрый день. Евгений! Хорошая работа!


Сейчас наступает не менее важная часть разработки - рефакторинг кода. Далее я отправлю список замечаний.
Ваша задача внимательно изучить их и внести исправления в свой код

---

https://github.com/majik48/frontend-project-lvl1/blob/220afda6a2851679b19474203ee3ab9a57980608/README.md

Ссылка на codeclimate ведет на тестовый репозиторий codeclimate

Не хватает badge на hexlet-check как и самой проверки, судя по всему потому что проект стартовал раньше чем были созданны эти проверки

Нужно попробовать подготовить проект ещё раз: Для этого нужно вернуться на шаг подготовки https://ru.hexlet.io/projects/44/members/3924/settings
И повторно разрешить доступ, если это не поможет обратиться за помощью ко мне в слаке

---

https://github.com/majik48/frontend-project-lvl1/blob/220afda6a2851679b19474203ee3ab9a57980608/package.json#L4

Это описание попадает в npm репозиторий, разработчикам наткнувшийся на новый пакет было бы приятно если бы из этого описания сразу можно было понять о чем проект

https://github.com/majik48/frontend-project-lvl1/blob/220afda6a2851679b19474203ee3ab9a57980608/package.json#L5

В первом проекте мы ничего не импортируем из проекта, эта инструкция лишняя

---

https://github.com/majik48/frontend-project-lvl1/blob/220afda6a2851679b19474203ee3ab9a57980608/package.json#L13

Также неплохо бы добавить имя автора

---

https://github.com/majik48/frontend-project-lvl1/blob/220afda6a2851679b19474203ee3ab9a57980608/src/cli.js#L3-L8

https://github.com/majik48/frontend-project-lvl1/blob/220afda6a2851679b19474203ee3ab9a57980608/src/games/brain-calc-game.js#L10

Функция нарушает принцип [CQRS ](https://ru.wikipedia.org/wiki/CQRS)

А также на 5 шаге https://ru.hexlet.io/projects/44/members/14943?step=5 сказано

```
Файл cli.js не предназначен для описания логики игр.
Файлы, которые мы добавили ранее (src/cli.js, bin/brain-games.js), оставьте как есть и не смешивайте с остальным кодом.
```

---

https://github.com/majik48/frontend-project-lvl1/blob/220afda6a2851679b19474203ee3ab9a57980608/bin/brain-calc.js#L5

Функции это всегда глаголы, подобробнее о хорошем наименование можно почитать [здесь](https://ru.hexlet.io/blog/posts/naming-errors-1)

---

https://github.com/majik48/frontend-project-lvl1/tree/220afda6a2851679b19474203ee3ab9a57980608/src/games

`games` в имени файла здесь лишний, из контекста (они находятся в директории games) уже понятно что это файлы игр


---

https://github.com/majik48/frontend-project-lvl1/blob/220afda6a2851679b19474203ee3ab9a57980608/src/games/brain-calc-game.js#L19-L28

Такие операции нужно выносить в отдельные функции

---

https://github.com/majik48/frontend-project-lvl1/blob/220afda6a2851679b19474203ee3ab9a57980608/src/games/brain-calc-game.js#L9-L38


https://ru.hexlet.io/projects/44/members/3924?step=6

`С введением второй игры у вас появляется общая для всех игр логика (Эту логику стоит поместить в файл src/index.js). Главная задача этого шага – построить архитектуру запуска игр так, чтобы эта логика была в одном месте и управляла играми.`

Общая логика всех игры должна быть выделена в отдельный движок, сама игра должна предоставлять движку игровые данные, а движок должен отвечать за сам процесс игры и должен быть описан в `src/index.js`

Этот комментарий касается всех игр

---


Все вопросы, которые возникают, задавайте мне в слаке. Там мы их сможем оперативно решить.
