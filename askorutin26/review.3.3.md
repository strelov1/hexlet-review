Извиняюсь за такую огромную задержку, проект выпал из моего поле зрения((
    
https://github.com/askorutin26/frontend-project-lvl3/blob/bdc0866dc51ad7e9c6c3b608517738ceeec65339/src/watcher.js#L20

Мы уже храним информацию о урл в фидах
https://github.com/askorutin26/frontend-project-lvl3/blob/bdc0866dc51ad7e9c6c3b608517738ceeec65339/src/handler.js#L20


---

https://github.com/askorutin26/frontend-project-lvl3/blob/main/src/watcher.js#L56

Имя функции слишком общее, без погружения в контекст сложно понять ее назначение

---

https://github.com/askorutin26/frontend-project-lvl3/blob/bdc0866dc51ad7e9c6c3b608517738ceeec65339/src/watcher.js#L58

Удобнее все же будет работать не с результатом всех запросов а с конкретным фидом,
нужно сделать отдельную функцию которая принимает фид и стейт, и по окончанию добавлять новые посты для конкретного фида 


Тогда не придется делать это, так как ид фида у нас уже будет известно

https://github.com/askorutin26/frontend-project-lvl3/blob/bdc0866dc51ad7e9c6c3b608517738ceeec65339/src/watcher.js#L66

---

https://github.com/askorutin26/frontend-project-lvl3/blob/bdc0866dc51ad7e9c6c3b608517738ceeec65339/src/watcher.js#L68

Если массив пустой итерации по нему все равно не будет, эта проверка не имеет смысла

---

https://github.com/askorutin26/frontend-project-lvl3/blob/bdc0866dc51ad7e9c6c3b608517738ceeec65339/src/watcher.js#L69-L77

Не забываем про CQRS, Нужно разделить процесс на два этапа - разметка данных (добавление id и feed_id)

```
const newPosts = diff.map((post) => {...post, postId: _.uniqueId('post_'), feedID: id })
```
---

https://github.com/askorutin26/frontend-project-lvl3/blob/bdc0866dc51ad7e9c6c3b608517738ceeec65339/src/watcher.js#L59

Еще важный момент, в Promise.then у нас будет только успешного добавление, это значит при первой же ошибке сети или проблемам на сайте какого-то фида, вся наша очередь остановится

---

https://github.com/askorutin26/frontend-project-lvl3/blob/bdc0866dc51ad7e9c6c3b608517738ceeec65339/src/handler.js#L11

try в текущем контексте усложняет обработку ошибки, приходится делать в 2х местах одно и тоже

---

https://github.com/askorutin26/frontend-project-lvl3/blob/bdc0866dc51ad7e9c6c3b608517738ceeec65339/src/handler.js#L35

Здесь перехватывается большой участок кода, по этому ошибка может быть совсем не парсинга,
правильнее будет поменять саму ошибку парсера соответственно

https://github.com/askorutin26/frontend-project-lvl3/blob/bdc0866dc51ad7e9c6c3b608517738ceeec65339/src/rssParser.js#L5

```
if (error) {
    const error = new Error(error.textContent);
    error.isParsingError = true;
    throw error;
}
```

---

https://github.com/askorutin26/frontend-project-lvl3/blob/bdc0866dc51ad7e9c6c3b608517738ceeec65339/src/handler.js#L39

А здесь в axios это уже есть e.isAxiosError

---

https://github.com/askorutin26/frontend-project-lvl3/blob/bdc0866dc51ad7e9c6c3b608517738ceeec65339/src/handler.js#L13-L15

В таком случае удобнее получать значение через распаковку объекта

const { rssTitle, description, postElems } = rssData

---

https://github.com/askorutin26/frontend-project-lvl3/blob/bdc0866dc51ad7e9c6c3b608517738ceeec65339/src/watcher.js#L93

Обработчик навшенивается при каждом рендере, куда экономичнее это сделать 1 раз при старте приложения, повесив событие отслеживания клика на весь контейнер с постами, а уже при нажатии определять, туда ли мы нажали, и на основании этого определять делать что-либо или нет

https://github.com/askorutin26/frontend-project-lvl3/blob/bdc0866dc51ad7e9c6c3b608517738ceeec65339/src/handler.js#L83


---

https://github.com/askorutin26/frontend-project-lvl3/blob/1b1210a2f25e45676b303221c02896abc969054b/src/handler.js#L64

Не нашел использования этой функции

---

https://github.com/askorutin26/frontend-project-lvl3/blob/1b1210a2f25e45676b303221c02896abc969054b/src/handler.js#L51

Предыдущие урл можно взять из фидов `feed.map({url} => url)`

---

https://github.com/askorutin26/frontend-project-lvl3/blob/1b1210a2f25e45676b303221c02896abc969054b/src/view.js#L43

инстанс i18n нужно прокидывать в стейт не глобально, а после его создания и настройки локали

он будет тут 

https://github.com/askorutin26/frontend-project-lvl3/blob/1b1210a2f25e45676b303221c02896abc969054b/src/watcher.js#L43

дальше нужно прокинуть в функции render*