Поздравляю с успешным завершением проекта!

Небольшое домашнее задание, которое поможет сделать ваш проект еще лучше :)

_________________

https://github.com/rootyss/frontend-project-lvl1/blob/27af4f7b992e6b0660911a6b6c8db8e83e2b45de/src/index.js#L4

Есть вопросы к имени функции, т.к. функция не только имя получает, но и приветствует его - это нарушает принцип [CQRS ](https://ru.wikipedia.org/wiki/CQRS)

_________________


https://github.com/rootyss/frontend-project-lvl1/blob/27af4f7b992e6b0660911a6b6c8db8e83e2b45de/src/games/prime.js#L11

Вот с i вопросов нет, а что такое s – не понятно.

_________________


https://github.com/rootyss/frontend-project-lvl1/blob/27af4f7b992e6b0660911a6b6c8db8e83e2b45de/src/index.js#L10

Точнее будет roundsCount

_________________


https://github.com/rootyss/frontend-project-lvl1/blob/27af4f7b992e6b0660911a6b6c8db8e83e2b45de/src/games/calc.js#L7

getCorrectAnswer - лучше уж так.

_________________

https://github.com/rootyss/frontend-project-lvl1/blob/27af4f7b992e6b0660911a6b6c8db8e83e2b45de/src/games/progression.js#L17

Здесь также лучше genGameQuestion.

_________________

Аналогично здесь:

https://github.com/rootyss/frontend-project-lvl1/blob/27af4f7b992e6b0660911a6b6c8db8e83e2b45de/src/games/prime.js#L19

_________________

https://github.com/rootyss/frontend-project-lvl1/blob/27af4f7b992e6b0660911a6b6c8db8e83e2b45de/src/games/progression.js#L18

И тогда уж не progWithHiddenElem, а question. Старайтесь думать в терминах доменной области, если вы хотели
работу с прогрессией выделить в свою доменную область и работать в этих терминах, то такие имена бы подошли,
но нужно было бы и в коде эти два слоя явно разнести, а так у нас смешалось терминология игры
с формирование запроса и работа с прогрессией

_________________

https://github.com/rootyss/frontend-project-lvl1/blob/main/.eslintignore

Если игнорить нечего, то и файл добавлять нет смысла.

_________________

Также помните, что это ваше приложение, и по мере получения новых знаний вы можете его дорабатывать, улучшать и расширять.