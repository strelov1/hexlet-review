Добрый день. Артем! У вас получилось написать собственное приложение. Это очень хорошо.

Сейчас наступает не менее важная часть разработки - рефакторинг кода. Далее я отправлю список замечаний.
Ваша задача внимательно изучить их и внести исправления в свой код

---

https://github.com/askorutin26/frontend-project-lvl1/blob/84bca3847f0bf60241495ddaa384c45209104dce/package.json#L5

https://github.com/askorutin26/frontend-project-lvl1/blob/84bca3847f0bf60241495ddaa384c45209104dce/package.json#L21

Не хватает описания (description) и автора проекта

Это описание попадает в npm репозиторий, разработчикам наткнувшийся на новый пакет было бы приятно если бы из этого описания сразу можно было понять о чем проект

---

https://github.com/askorutin26/frontend-project-lvl1/blob/84bca3847f0bf60241495ddaa384c45209104dce/package.json#L13

В первом проекте мы ничего не импортируем из проекта, эта инструкция лишняя

---

https://github.com/askorutin26/frontend-project-lvl1/blob/84bca3847f0bf60241495ddaa384c45209104dce/.gitignore#L1

При такой записи будут игнорироваться как файлы с именем node_modules, так и директории с таким же именем. У нас задача игнорировать директорию node_modules в корне проекта.

Изучите таблицу паттернов по .gitignore и внесите необходимые изменения https://www.atlassian.com/git/tutorials/saving-changes/gitignore

---

https://github.com/askorutin26/frontend-project-lvl1/blob/84bca3847f0bf60241495ddaa384c45209104dce/README.md

На странице должны отображаться сами аскинемы, а не ссылки на них. Так проект будет выглядеть более привлекательно для потенциальных работодателей, которые будут просматривать ваш репозиторий.

Просмотрите как можно встроить на страницу аскинему https://asciinema.org/docs/embedding

Также в README можно включить инструкцию установки в текстовом формате, чтобы была возможность установить скопировав команды

Ссылка на codeclimate ведет на тестовый репозиторий codeclimate

---

https://github.com/askorutin26/frontend-project-lvl1/tree/84bca3847f0bf60241495ddaa384c45209104dce/games

Директория games является часть исходного кода и должна находится в директории src

---

https://ru.hexlet.io/projects/44/members/15112?step=6

`С введением второй игры у вас появляется общая для всех игр логика (Эту логику стоит поместить в файл src/index.js). Главная задача этого шага – построить архитектуру запуска игр так, чтобы эта логика была в одном месте и управляла играми.`

Общая логика всех игры должна быть выделена в отдельный движок, сама игра должна предоставлять движку игровые данные, а движок должен отвечать за сам процесс игры и должен быть описан в `src/index.js`

---

https://github.com/askorutin26/frontend-project-lvl1/blob/main/games/brain-Calc-Engine.js#L19-L29

Сам подход супер! Но лучше выделить такой код в отдельную функцию, сгенерированные числа передавать в виде аргументов, и определять не внутри цикла а на уровне модуля

---

https://github.com/askorutin26/frontend-project-lvl1/blob/main/games/brain-Calc-Engine.js#L33

Лучше стараться избегать таких неявных преобразований

---

https://github.com/askorutin26/frontend-project-lvl1/blob/main/games/brain-Calc-Engine.js#L14

Тут у нас появились магические числа, подробнее о них https://ru.hexlet.io/blog/posts/magic-numbers

---

https://github.com/askorutin26/frontend-project-lvl1/blob/main/games/brain-Calc-Engine.js#L7-L8

Генерацию рандомных чисел стоит выделить в отдельную функцию, тем более она используется не в одной игре, таким образом ее можно будет переиспользовать

---

https://github.com/askorutin26/frontend-project-lvl1/blob/main/games/brain-Even-Engine.js#L16-L19

Здесь есть проблемы с разделением уровней абстракции, советую ознакомиться с этой статей
https://ru.hexlet.io/blog/posts/sovershennyy-kod-proektirovanie-funktsiy
в ней как раз разбирается этот пример

---

Все вопросы, которые возникают, задавайте мне в слаке. Там мы их сможем оперативно решить.
