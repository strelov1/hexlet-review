Отличная работа! Остались совсем мелкие штрихи

https://github.com/Finnko/frontend-project-lvl3/blob/96aadfe2ef809b8f196e0a71fe157faa3a24e63f/src/app.js#L51

Здесь отлично бы подошла структура данных Set

Вложенность в этом месте, немного усложняет структуру обращения к постам, можно viewedPosts разместить на верхнем уровне и избавиться от list

---

https://github.com/Finnko/frontend-project-lvl3/blob/96aadfe2ef809b8f196e0a71fe157faa3a24e63f/src/app.js#L61

Название функции смущает, polling это определенный процесс взаимодействия с сервером, и эта функция не занимается им

---

https://github.com/Finnko/frontend-project-lvl3/blob/96aadfe2ef809b8f196e0a71fe157faa3a24e63f/src/parser.js#L21-L23

https://ru.hexlet.io/blog/posts/sovershennyy-kod-razdelenie-polucheniya-i-ispolzovaniya

---

```
const error = new Error(errorBlock.textContent);
```

Дальнейшая отладка упроститься если прокинуть текст оригинальной ошибки в ошибку, это ошибка именно для отладки не для клиента

---

https://github.com/Finnko/frontend-project-lvl3/blob/96aadfe2ef809b8f196e0a71fe157faa3a24e63f/src/validation.js#L4-L11

Локаль нужно устанавливать при инициализации приложения, переводы ошибок здесь тоже не нужно держать, только константы, саму трансляцую делать нужно во view

---

https://github.com/Finnko/frontend-project-lvl3/blob/96aadfe2ef809b8f196e0a71fe157faa3a24e63f/src/view/renderPosts.js#L38-L41

Выглядит странновато, потому что везде теперь делается через createElement, непонятно почему здесь так