Добрый день. Николай! Отличная работа!

Сейчас наступает не менее важная часть разработки - рефакторинг кода. Далее я отправлю список замечаний.
Ваша задача внимательно изучить их и внести исправления в свой код

---

https://github.com/enareel/frontend-project-lvl1/blob/cc4a874fa97fcb44b3c468ba255ca0e992987a99/README.md

На странице должны отображаться сами аскинемы, а не ссылки на них. Так проект будет выглядеть более привлекательно для потенциальных работодателей, которые будут просматривать ваш репозиторий. Просмотрите как можно встроить на страницу аскинему https://asciinema.org/docs/embedding

---

Также в README можно включить инструкцию установки в текстовом формате, чтобы была возможность установить скопировав команды

---

Ссылка на codeclimate ведет на тестовый репозиторий codeclimate

---

https://github.com/enareel/frontend-project-lvl1/blob/cc4a874fa97fcb44b3c468ba255ca0e992987a99/package.json#L5

Это описание попадает в npm репозиторий, разработчикам наткнувшийся на новый пакет было бы приятно если бы из этого описания сразу можно было понять о чем проект

---

https://github.com/enareel/frontend-project-lvl1/blob/cc4a874fa97fcb44b3c468ba255ca0e992987a99/package.json#L6

В первом проекте мы ничего не импортируем из проекта, эта инструкция лишняя


---

https://github.com/enareel/frontend-project-lvl1/blob/cc4a874fa97fcb44b3c468ba255ca0e992987a99/bin/brain-calc.js#L6-L9

Функции это всегда глаголы, подобробнее о хорошем наименование можно почитать [здесь](https://ru.hexlet.io/blog/posts/naming-errors-1)

---

https://github.com/enareel/frontend-project-lvl1/blob/cc4a874fa97fcb44b3c468ba255ca0e992987a99/bin/brain-calc.js#L5-L9

В бинарном файле должен быть только запуск игры, лучше вынести запуск движка в файл с игрой, а бинарных файлах только запускать


---

https://github.com/enareel/frontend-project-lvl1/blob/cc4a874fa97fcb44b3c468ba255ca0e992987a99/src/cli.js#L15

Эта функция кроме запроса приветствия пользователя, выполняет и другие операции, тем самым нарушает [CQRS](https://ru.wikipedia.org/wiki/CQRS).


---

https://github.com/enareel/frontend-project-lvl1/blob/cc4a874fa97fcb44b3c468ba255ca0e992987a99/src/engine.js#L24

На 5 шаге указано https://ru.hexlet.io/projects/44/members/15767?step=5

```
Файл cli.js не предназначен для описания логики игр.
Файлы, которые мы добавили ранее (src/cli.js, bin/brain-games.js), оставьте как есть и не смешивайте с остальным кодом.
```

---

https://github.com/enareel/frontend-project-lvl1/blob/cc4a874fa97fcb44b3c468ba255ca0e992987a99/src/engine.js#L9

Количественное значение, подробнее о именовании (#Количество) https://ru.hexlet.io/blog/posts/naming-in-programming


---

https://github.com/enareel/frontend-project-lvl1/blob/cc4a874fa97fcb44b3c468ba255ca0e992987a99/src/engine.js#L29

Вместо изменений это переменной лучше сразу выводить это сообщение в нужном месте 
https://github.com/enareel/frontend-project-lvl1/blob/cc4a874fa97fcb44b3c468ba255ca0e992987a99/src/engine.js#L43

А код после прерывать вместе со всей функцией с помощью `return`

---

https://github.com/enareel/frontend-project-lvl1/blob/cc4a874fa97fcb44b3c468ba255ca0e992987a99/src/engine.js#L50

А вот этого возврата от игры тоже никто не ждет, если нужно прервать ничего не выводя то делается это с помощью `return ;`

---

https://github.com/enareel/frontend-project-lvl1/blob/cc4a874fa97fcb44b3c468ba255ca0e992987a99/src/utils.js#L12

Имя функции не соответствует ее действию, она генерирует рандомное число а не показывает его, имена аргументов также не отражают их смысл `min, max`


---

https://github.com/enareel/frontend-project-lvl1/tree/cc4a874fa97fcb44b3c468ba255ca0e992987a99/games

Директория src должна содержать исходный код программы,
Игры также являются исходным кодом, в наименовании постфикс `-src` лишний, если бы они находились в нужной директории, из контекста было бы ясно что это исходный код

---

https://github.com/enareel/frontend-project-lvl1/blob/76e83d5d66f5b60b62741afcf1f8fb94211305b2/games/brain-calc-src.js#L8

В Js с большой буквы принято именовать классы https://mentoor.io/posts/studlycase-vs-camelcase-vs-snakecase/1

---

https://github.com/enareel/frontend-project-lvl1/blob/76e83d5d66f5b60b62741afcf1f8fb94211305b2/games/brain-calc-src.js#L41

Здесь лимиты все таки мин и макс, left, right это не совсем отражает смысл

---

https://github.com/enareel/frontend-project-lvl1/blob/76e83d5d66f5b60b62741afcf1f8fb94211305b2/games/brain-calc-src.js#L49

expression формируется для пользователя игры, а для вычисления у нас же есть все нужные переменные выше

---

https://github.com/enareel/frontend-project-lvl1/blob/76e83d5d66f5b60b62741afcf1f8fb94211305b2/games/brain-calc-src.js#L24

Подход с индексами это по сути те же магические переменные, можно было бы создать объект с перечислением на подобие с `Limit`

---

https://github.com/enareel/frontend-project-lvl1/blob/76e83d5d66f5b60b62741afcf1f8fb94211305b2/games/brain-calc-src.js#L25

Не очень понятно для чего здесь столько плюсов, если для преобразования формата данных, то это делать нужно точно не здесь

---

https://github.com/enareel/frontend-project-lvl1/blob/76e83d5d66f5b60b62741afcf1f8fb94211305b2/games/brain-calc-src.js#L30-L31

Смысл правильный, но можно сделать лучше, подробнее можно почитать [здесь](https://ru.hexlet.io/blog/posts/sovershennyy-kod-defolty-v-svitchah)


---

https://github.com/enareel/frontend-project-lvl1/blob/76e83d5d66f5b60b62741afcf1f8fb94211305b2/games/brain-even-src.js#L22

---



https://github.com/enareel/frontend-project-lvl1/blob/76e83d5d66f5b60b62741afcf1f8fb94211305b2/games/brain-even-src.js#L36

Идея интересная, но код выглядит запутаннее, приходится изучать функцию getKeyByValue прежде чем понять что происходит, в текущем конексте, можно было сделать проще

```
const answer = isEven(question) ? 'yes' : 'no';
```

---

https://github.com/enareel/frontend-project-lvl1/blob/76e83d5d66f5b60b62741afcf1f8fb94211305b2/games/brain-prime-src.js#L45

`-Limit.LEFT + 2` Может сразу указать нужный лимит?


---

Давай пока поработаем над этими рекомендациями, потом дам следующую порцию

Для первой итерации очень даже неплохо, главное что ты самостоятельно с первого раза догадался как правильно организовать архитектуру с выделением общего движка игры!

---

Все вопросы, которые возникают, задавайте мне в слаке. Там мы их сможем оперативно решить.
