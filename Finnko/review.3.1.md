
Привет. Поздравляю с завершение проекта, осталось совсем чуть чуть - довести его до идеала :-)


https://github.com/Finnko/frontend-project-lvl3/blob/main/.gitignore#L3-L4

https://github.com/Finnko/frontend-project-lvl3/blob/main/.eslintignore#L1-L2

Чтобы брались только директории необходимо указывать в таком формате

```
/node_modules/
/dist/
```

---


https://github.com/Finnko/frontend-project-lvl3/blob/main/package.json#L57

https://github.com/Finnko/frontend-project-lvl3/blob/main/package.json#L59

Это для чего?

---

https://github.com/Finnko/frontend-project-lvl3/blob/main/package.json#L60-L61

Эти зависимости необходимы только для сборки проекта и в prod режиме не нужны, необходимо перенести их в devDependencies

---

На первом шаге есть такая инструкции

```
Выполните все необходимые приготовления (Github Actions, linter, CodeClimate, badges).
```

Она говорит о том что нам необходимо настроить линтинг и все те же баджи что и во 2ом проекте

https://github.com/Finnko/frontend-project-lvl2

https://github.com/Finnko/frontend-project-lvl2/blob/main/.github/workflows/tests-check.yml


---

https://github.com/Finnko/frontend-project-lvl3/blob/main/src/app.js#L44-L57

Здесь в dom завязываемся на сликшом много деталей, это происходит из-за не правильно спроектированного  view, обо view ниже, а здесь достаточно завязать на главных блоках (форма, посты фиды и контейнер для модального окна)


---

https://github.com/Finnko/frontend-project-lvl3/blob/main/src/api/makeRequest.js#L6

Url лучше собрать с помощью встроенного класса new URL()

---

https://github.com/Finnko/frontend-project-lvl3/blob/main/src/api/makeRequest.js#L12-L15

В ошибке из axios уже есть признак который позволяет определить что произошла ошибка в нем `e.isAxiosError`

---

https://github.com/Finnko/frontend-project-lvl3/blob/main/src/app.js#L68

https://github.com/Finnko/frontend-project-lvl3/blob/main/src/app.js#L95

Хранить сообщение об успешной загрузке в состоянии не нужно, для того чтобы определить что загрузка прошла успешна мы уже имеем ```state.form.processState = 'success'```


---

https://github.com/Finnko/frontend-project-lvl3/blob/main/src/app.js#L69

В данном контексте самой ошибки достаточно одной, каждая ошибка блокирует процесс и дальше не дает пройти пока не устранена эта ошибка

---

https://github.com/Finnko/frontend-project-lvl3/blob/main/src/view/renderFeeds.js#L3-L23

Вполне рабочий подход, но есть 2 проблемы:

Цель проекта закрепить полученные ранее знания а именно работа Dom

И второй более важный момент такой подход не даст нам гибкости, это особенно проявляется здесь

https://github.com/Finnko/frontend-project-lvl3/blob/main/src/view/renderForm.js#L4-L27

При каждом изменении нам приходится думать о предыдущем состоянии включать или отключать блокировку на пример, по сути у нас dom с таким подходом начинает хранить состояние, если бы мы каждый раз констрировали dom, в таком случае нам было бы достаточно только добавлять блокировку только в том месте где она нужна.

В итоге что нужно сделать: Собирать элементы dom каждый раз заново через document.createElement и вставлять уже в реальный dom

---

https://github.com/Finnko/frontend-project-lvl3/blob/main/src/view/index.js#L6

Для функции render не нужны будут поля value, prevValue
Для обновления состояния каждого элемента достаточно забрать весь watchedState и брать обновленные значение напрямую о туда, не задумаывася о том то ли значение мы подхватили или нет

Также render должен принимать инстанс i18n так как переводы в состоянии хранить нельзя, сам перевод нужно делать непосредственно во view 
