
https://github.com/rootyss/frontend-project-lvl3/blob/bd31c49158890a4bcf4769deec65ebba6da6cc70/package.json#L38

https://github.com/rootyss/frontend-project-lvl3/blob/bd31c49158890a4bcf4769deec65ebba6da6cc70/package.json#L45

https://github.com/rootyss/frontend-project-lvl3/blob/bd31c49158890a4bcf4769deec65ebba6da6cc70/package.json#L42

Неиспользуемые зависимости
_________________

https://github.com/rootyss/frontend-project-lvl3/blob/bd31c49158890a4bcf4769deec65ebba6da6cc70/package.json#L7

Тестов нет, команда осталась


_________________

https://github.com/rootyss/frontend-project-lvl3/blob/main/README.md

Не хватает инструкций о том как проект установить

Примеры оформления README 

https://github.com/Hexlet/cli/blob/main/README.md

https://github.com/Hexlet/hexlet-cv/blob/master/README.md

https://github.com/Hexlet/hexlet-sicp/blob/master/README.md

_________________

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/app.js#L27

Этот метод не генерирует ошибку, а определяет ее тип: detect|get|identify|find|parse|ErrorType

Функцию лучше сделать чистой, чтобы она только возвращала тип, тогда не нужно будет ей передавать state

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/app.js#L33-L35

else здесь лишний
_________________

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/app.js#L32

Лучше здесь также определять тип, так у нас парсер стал знать еще и локале, хотя ему это незачем

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/utils.js#L16

А вот в самом парсере лучше передать оригинальный текст ошибки, это упростит отладку в будущем

```
new Error(parsererror.textContent);
```
_________________

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/app.js#L104-L112

Сейчас валидатор использует watchedState из глобальной области видимости, лучше определить эту функцию на уровне модуля
и передать список фидов туда в виде аргумента

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/app.js#L105

Неплохо бы добавить валидацию на наличие поле `required`, хоть в input есть уже такая встроенная функция, не стоит на нее опираться,
так как не во всех браузерах реализована ее поддержка, и она тривиально отключается, 
в данном контексте конечно ничего страшного не произойдет если пользователь отправить пустой запрос, но в некоторых ситуациях это может сломать что-нибудь, 
поэтому стоит думать о таких моментах всегда


_________________

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/app.js#L136-L139

Тут более подходящим было добавить предусловие с выходом

https://ru.hexlet.io/courses/js-functions-hard-way/lessons/guard-expression/theory_unit


_________________

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/render.js#L127-L132

в case обычно используют такой подход чтобы объединить условия

```
    case 'posts':
    case 'visitedPostsId':
      renderPostsElements(state, elements, i18nInstance);
      break;
```
_________________

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/render.js#L77-L85

Построение некоторых объектов, стоит выделить в отдельные функции

```
buildLinkElement = () => {
    const aEl = document.createElement('A');
    return aEl;
}

```
_________________

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/render.js#L79-L81

тут одинаковое условие, предпочтительнее использовать if 

```
if (state.visitedPostsId.includes(String(id))) {
     aEl.classList.add('fw-normal');
} else {
    aEl.classList.add('fw-bold');
}
```

Еще лучше это условие будет читаться, если мы перед выводом обогатим коллекцию этим параметром

```
const posts = state.posts.map((post) => ({
    ...post,
    isVisited: state.visitedPostsId.includes(post.id) 
}))

if (post.isVisited) {
     aEl.classList.add('fw-normal');
} else {
}
```

https://github.com/rootyss/frontend-project-lvl3/blob/main/src/render.js#L87

Функция называется getAttr - а занимается тем что устанавливает атрибуты

_________________


https://github.com/rootyss/frontend-project-lvl3/blob/main/src/render.js#L108

Тут лучше подойдет функция .find массива