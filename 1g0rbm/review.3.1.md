Добрый день. Игорь! 
Знаю проект не из - легких ты хорошо потрудился!

И так приступим к рефакторингу

https://github.com/1g0rbm/frontend-project-lvl3/blob/21dccf06c5911f31450a5116de721f959bf60a07/README.md

Не хватает инструкций по установке сборке и тестировании проекта

_________________

https://frontend-project-lvl3-1g0rbm.vercel.app/

Внешний вид формы отличается от эталона https://frontend-l3-rss-reader.herokuapp.com/

_________________


https://github.com/1g0rbm/frontend-project-lvl3/blob/21dccf06c5911f31450a5116de721f959bf60a07/src/app.js#L12-L13

https://ru.hexlet.io/projects/11/members/16293?step=1

Важно! Проект должен быть построен на промисах. Использовать async/await нельзя

_________________


https://github.com/1g0rbm/frontend-project-lvl3/blob/21dccf06c5911f31450a5116de721f959bf60a07/src/parseRss.js#L20-L31

Рекомендую ознакомиться
https://ru.hexlet.io/blog/posts/sovershennyy-kod-razdelenie-polucheniya-i-ispolzovaniya

_________________

https://github.com/1g0rbm/frontend-project-lvl3/blob/21dccf06c5911f31450a5116de721f959bf60a07/src/parseRss.js#L17

Парсер чистая функция, он не должен менять структуру. Установка id - не ответственность парсера.

_________________

https://github.com/1g0rbm/frontend-project-lvl3/blob/21dccf06c5911f31450a5116de721f959bf60a07/src/loadRss.js#L5-L15

Добавление прокси лучше отделить от http клиента


_________________

https://github.com/1g0rbm/frontend-project-lvl3/blob/21dccf06c5911f31450a5116de721f959bf60a07/src/app.js#L93-L98

Валидацию пользовательских данных имеет смысл вынести в отдельную функцию

_________________


https://github.com/1g0rbm/frontend-project-lvl3/blob/21dccf06c5911f31450a5116de721f959bf60a07/src/Timer.js#L13-L14

Если у нас будет большой список rss, то код загрузки не будет успевать обновлять информацию по всем rss до того как начнется следующая итерация обновления