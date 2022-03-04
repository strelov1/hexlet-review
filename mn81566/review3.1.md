Поздравляю с завершением 3 проекта, приступим к ревью

---

https://github.com/mn81566/frontend-project-lvl3/tree/836d99f32e7b6bd08bfb6d08ef50436075c1bcec#readme

Не хватает инструкции для установки и использованию, а также описания проекта

---

https://github.com/mn81566/frontend-project-lvl3/actions/runs/1798823319

Проект не проходит тестов

```
app_1  |     Cannot find module '/project/code/index.js' from '__tests__/10-prepare.test.js'
```

Тесты ожидают что в файле package.json https://github.com/mn81566/frontend-project-lvl3/blob/836d99f32e7b6bd08bfb6d08ef50436075c1bcec/package.json#L5 будет ссылаться на файл в котором будет эспортироваться по умолчанию главная функция приложения, об этом подробнее описано на 7 шаге проекта https://ru.hexlet.io/projects/11/members/17534?step=7

---

https://github.com/mn81566/frontend-project-lvl3/runs/5076590063?check_suite_focus=true

Линтер тоже не проходит

https://github.com/mn81566/frontend-project-lvl3/blob/836d99f32e7b6bd08bfb6d08ef50436075c1bcec/src/view.js#L123-L131

Как я упоминал на созвоне, эту проблему можно решить с помощью фрагмента https://developer.mozilla.org/en-US/docs/Web/API/Document/createDocumentFragment

```
const fragment = document.createDocumentFragment();

fragment.appendChild(urlInputNode);

fragment.appendChild(feedbackNode);
```

---

https://github.com/mn81566/frontend-project-lvl3/blob/836d99f32e7b6bd08bfb6d08ef50436075c1bcec/src/view.js#L44-L88

Не работает, значит и нет причин хранить в кодовой базе, с историей отлично справляется гит

---

https://github.com/mn81566/frontend-project-lvl3/blob/836d99f32e7b6bd08bfb6d08ef50436075c1bcec/src/parse.js#L8-L11

Именно так, можно прокинуть исходную ошибку

```
throw new Error(errorNode.textContent);
```

---

https://github.com/mn81566/frontend-project-lvl3/blob/836d99f32e7b6bd08bfb6d08ef50436075c1bcec/src/parse.js#L13

https://github.com/mn81566/frontend-project-lvl3/blob/836d99f32e7b6bd08bfb6d08ef50436075c1bcec/src/parse.js#L24

Задача парсера как ни странно парсить данные, это простая чистая функция принимающая на вход xml, возвращающая объект, она ничего не должна знать о том как этот объект будут использовать дальше, а идшинки это нужное только для ui стейта

---

https://github.com/mn81566/frontend-project-lvl3/blob/836d99f32e7b6bd08bfb6d08ef50436075c1bcec/src/controller.js#L36

Это действие стоит выделить в отдельную функцию, что касается fetch, то на 4 шаге есть список ссылок на библиотеки предлагаемых для использования в проекте и в качестве http клиента там предлагается axios

---

https://github.com/mn81566/frontend-project-lvl3/blob/836d99f32e7b6bd08bfb6d08ef50436075c1bcec/src/index.js#L6

Такая конструкция выглядит странновато, можно ее упростить до

```
const i18nextInstance = i18next.createInstance();

i18nextInstance.init({
    lng: 'ru',
    debug: true,
    resources: {
        ru,
        en,
    },
}).then(app)

```

---

https://github.com/mn81566/frontend-project-lvl3/blob/836d99f32e7b6bd08bfb6d08ef50436075c1bcec/src/app.js#L30

Ошибок одновременно все же у нас может быть не больше 1, в этом случае использовать массив будет некорректно

---

https://github.com/mn81566/frontend-project-lvl3/blob/836d99f32e7b6bd08bfb6d08ef50436075c1bcec/src/app.js#L29

url в форме также 1, а загруженные фиды хранятся в feed;

---

https://github.com/mn81566/frontend-project-lvl3/blob/836d99f32e7b6bd08bfb6d08ef50436075c1bcec/src/app.js#L34-L42

Вот тут небольшой сумбур, не прочитва кода использующего не понять под что зарезервированные эти переменные в стейте

---

https://github.com/mn81566/frontend-project-lvl3/blob/836d99f32e7b6bd08bfb6d08ef50436075c1bcec/src/app.js#L26

Это избыточное состояние, form.processState уже может отображать все состояния формы
