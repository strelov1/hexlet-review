Осталось совсем чуть чуть, на финишной прямой

---

https://github.com/askorutin26/frontend-project-lvl3/blob/d5b685a94d559eb5ffe87b79ae72eeb03483301a/src/watcher.js#L17

Эта переменная отражает не просто состояние, а изначальное состояние, нужно дать ей соответствующее имя, чтобы не вводить зазблуждение

---


https://github.com/askorutin26/frontend-project-lvl3/blob/d5b685a94d559eb5ffe87b79ae72eeb03483301a/src/watcher.js#L20

У формы должно быть какое-то начальное состояние

---

https://github.com/askorutin26/frontend-project-lvl3/blob/d5b685a94d559eb5ffe87b79ae72eeb03483301a/src/watcher.js#L79

Запускать повторное обновление фида нужно, не только после успешного обновления всех постов, но и в случае если хоть один из фидов вернул ошибку тоже, для этого удобно будет использовать Promise.finally

---

https://github.com/askorutin26/frontend-project-lvl3/blob/d5b685a94d559eb5ffe87b79ae72eeb03483301a/src/watcher.js#L81-L83

А вот здесь ошибку отправлять в форму некорректно, после добавления фида, фид уже никак не связан с формой и такой вывод только введет в заблуждение пользователя
        
---

https://github.com/askorutin26/frontend-project-lvl3/blob/d5b685a94d559eb5ffe87b79ae72eeb03483301a/src/handler.js#L9-L34

Лучше вернуть запрос, для того чтоб не обрабатывать ошибку в двух местах

```
return makeQueryForRss(url)...

...

validateURL(normalizedURL, watchedState).then(() => {
return loadPosts(watchedState, form);
}).catch((error) => {
    const error = getErrName(err);

```
 
---

https://github.com/askorutin26/frontend-project-lvl3/blob/d5b685a94d559eb5ffe87b79ae72eeb03483301a/src/handler.js#L64-L65

Это не view, тут такое нельзя

---

https://github.com/askorutin26/frontend-project-lvl3/blob/d5b685a94d559eb5ffe87b79ae72eeb03483301a/src/errorName.js#L8

Наверное все же unkownError, default в этом контексте звучит странновато

Также для подобных функций избыточно создавать отдельный файл, принято такое помещать в utils.js


--- 

https://github.com/askorutin26/frontend-project-lvl3/blob/d5b685a94d559eb5ffe87b79ae72eeb03483301a/src/watcher.js#L96


Здесь как и в остальных рендераха, будет гибче если передать контейнер относительно, которого будет производится вставка

--- 


https://github.com/askorutin26/frontend-project-lvl3/blob/d5b685a94d559eb5ffe87b79ae72eeb03483301a/src/view.js#L170-L174

Это ветвление здесь не к чему, попробуй использовать фрагмент
https://developer.mozilla.org/ru/docs/Web/API/Document/createDocumentFragment
