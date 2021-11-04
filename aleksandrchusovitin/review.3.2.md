Привет. Отличная работа! Осталось не много косметики


https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/fa51a1f861bfa4470525efff305a64675a8ffc7b/src/init.js#L13-L25

Процесс загрузки постов стоит выделить в отдельную функцию

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/fa51a1f861bfa4470525efff305a64675a8ffc7b/src/init.js#L28

Магические числа, нужно определить константу с хорошо отражающий смысл содержимого именем

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/fa51a1f861bfa4470525efff305a64675a8ffc7b/src/init.js#L13

Отлично!, но еще остается проблема с тем, что если у нас не ответить хоть один сайт, у нас обновления остановятся навсегда

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/fa51a1f861bfa4470525efff305a64675a8ffc7b/src/getFeed.js#L3

Здесь параметры должны задаваться в другом виде

https://developer.mozilla.org/ru/docs/Web/API/URL

```
.searchParams.set('url', url);
.searchParams.set('disableCache', 'true')
```

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/fa51a1f861bfa4470525efff305a64675a8ffc7b/src/view.js#L17-L19

У нас не может появится ошибки, без изменения rssForm.state == 'error'
Такой код заставить обновиться дом 2 раза, хотя можно было бы всего 1 

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/fa51a1f861bfa4470525efff305a64675a8ffc7b/src/parser.js#L19

В парсере, не должно быть ничего про url, url в состоянии должен появиться в том месте где появляется id

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/fa51a1f861bfa4470525efff305a64675a8ffc7b/src/init.js#L114

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/fa51a1f861bfa4470525efff305a64675a8ffc7b/src/init.js#L108

Ошибку нужно очищать только в том кейсе когда ее нет, в иных случаях она замениться новой ошибкой

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/fa51a1f861bfa4470525efff305a64675a8ffc7b/src/locales/ru.js#L13-L20

Здесь немного не консистентно расположились данные, почему не выделить для всех ошибок отдельный объект errors, в таком случае не придется добавлять префиксы `Error, ErrorType`