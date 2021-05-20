Добрый день. Кристина! Работа Супер!

С первой попытки и так близко к идеалу!

Сейчас наступает не менее важная часть разработки - рефакторинг кода. Далее я отправлю список замечаний.
Ваша задача внимательно изучить их и внести исправления в свой код

---

https://github.com/isimyi/frontend-project-lvl1/blob/bbc79d788279da86d4ad03ca19a1abd22eb1c273/README.md

На странице должны отображаться сами аскинемы, а не ссылки на них. Так проект будет выглядеть более привлекательно для потенциальных работодателей, которые будут просматривать ваш репозиторий. Просмотрите как можно встроить на страницу аскинему https://asciinema.org/docs/embedding

---

Также в README можно включить инструкцию установки в текстовом формате, чтобы была возможность установить скопировав команды

---

https://github.com/isimyi/frontend-project-lvl1/commit/17177fb99a3c47d5016cdc24ab28556f8de14718

https://github.com/isimyi/frontend-project-lvl1/blob/bbc79d788279da86d4ad03ca19a1abd22eb1c273/package.json#L21

Не хватает описания (description) и автора проекта

Это описание попадает в npm репозиторий, разработчикам наткнувшийся на новый пакет было бы приятно если бы из этого описания сразу можно было понять о чем проект

---

https://github.com/isimyi/frontend-project-lvl1/blob/bbc79d788279da86d4ad03ca19a1abd22eb1c273/package.json#L4

В первом проекте мы ничего не импортируем из проекта, эта инструкция лишняя

---

https://github.com/isimyi/frontend-project-lvl1/blob/bbc79d788279da86d4ad03ca19a1abd22eb1c273/.gitignore#L2

При такой записи будут игнорироваться как файлы с именем node_modules, так и директории с таким же именем. У нас задача игнорировать директорию node_modules в корне проекта.

Изучите таблицу паттернов по .gitignore и внесите необходимые изменения https://www.atlassian.com/git/tutorials/saving-changes/gitignore

---

https://github.com/isimyi/frontend-project-lvl1/blob/bbc79d788279da86d4ad03ca19a1abd22eb1c273/bin/brain-calc.js

Данная часть проекта должна отвечать только за его запуск игры, сконфигурировать игру можно в файле самой игры, это замечание касается всех игр

---

https://github.com/isimyi/frontend-project-lvl1/blob/bbc79d788279da86d4ad03ca19a1abd22eb1c273/src/games/game-calc.js#L6-L10

Это супер!

---

https://github.com/isimyi/frontend-project-lvl1/blob/bbc79d788279da86d4ad03ca19a1abd22eb1c273/src/games/game-progression.js#L4-L19

Можно еще улучшить код разделить, формирование прогрессии и скрытие элемента на две независимых функции

---

https://github.com/isimyi/frontend-project-lvl1/blob/bbc79d788279da86d4ad03ca19a1abd22eb1c273/src/games/game-progression.js#L9-L14

При формировании прогрессии не стоит разделять на разные этапы, наполнение первого элемента от последующий в цикле, более явно будет делать это все в цикле

---

https://github.com/isimyi/frontend-project-lvl1/blob/bbc79d788279da86d4ad03ca19a1abd22eb1c273/src/index.js#L16

https://github.com/isimyi/frontend-project-lvl1/blob/bbc79d788279da86d4ad03ca19a1abd22eb1c273/src/index.js#L20

Логичнее было бы разделить на две переменные, описание игры и игровые данные,
так как в первом вызове, мы хоть и не используем игровые данные, мы их формируем в холостую, тоже касается и описания для последующих шагов в цикле

---

https://github.com/isimyi/frontend-project-lvl1/blob/bbc79d788279da86d4ad03ca19a1abd22eb1c273/src/index.js#L29

Данный ход у нас терминальный, с помощью return мы можем прерывать не только цикл, но и саму функцию

---

https://github.com/isimyi/frontend-project-lvl1/blob/bbc79d788279da86d4ad03ca19a1abd22eb1c273/src/index.js#L22

Движок не должен заботится о форматах данных, это уже ответственность игры, иначе нам не получится написать игру с чуствительным к регистру вводом

---

https://github.com/isimyi/frontend-project-lvl1/blob/bbc79d788279da86d4ad03ca19a1abd22eb1c273/src/index.js#L33-L35

Завершение цикла уже признак что все шаги пройдены, эта проверка лишняя

https://github.com/isimyi/frontend-project-lvl1/blob/bbc79d788279da86d4ad03ca19a1abd22eb1c273/src/index.js#L25

Также как и этот счетчик

---

Все вопросы, которые возникают, задавайте мне в слаке. Там мы их сможем оперативно решить.
