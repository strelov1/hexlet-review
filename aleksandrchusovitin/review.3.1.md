Привет. Поздравляю с завершение проекта, осталось совсем чуть чуть - довести его до идеала :-)

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/tree/89b3f5644df79b67d6c25e7ace6f7809646489fe#readme

Не хватает инструкции для установки и использованию, а также описания проекта

Также ссылка в описании раздел About справа - ведет на неработающий сайт
https://frontend-project-lvl3-three-delta.vercel.app/


---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/.eslintignore#L1-L2

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/.gitignore#L3-L4

При такой записи будут игнорироваться как файлы с именем node_modules, так и директории с таким же именем. У нас задача игнорировать директорию node_modules в корне проекта.

---


https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/init.js#L51

Все ошибки у нас относятся к форме, логично было бы их расположить в стейте формы rssFrom.error

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/init.js#L54

Здесь process выглядит избыточным, о каком процессе идет речь непонятно, в тоже время rssForm.state отлично справляется с описанием для чего это состояние служит

---


https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/init.js#L77-L79

Валидацию имеет смысл вынести в отдельную функцию, ```.object().shape(``` необходимо для валидации сложных объектов, в нашем случае было сразу ```yup.string().url()```

Также не хватает валидации на обязательность введения урл  
```required()```

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/init.js#L90-L91

Валидацию дублей, также нужно сделать через yup ```notOneOf```

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/init.js#L92

Этот атрибут дублирует часть функциональности processState

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/init.js#L103-L104

У нас есть уже валидация на то чтобы не было возможно загрузить один и тот же фид, это сравнение там здесь не нужно

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/init.js#L99-L101

Загрузку постов - загрузка по сети и парсинг - можно вынести в отдельную функцию - не перенести функционал обоих в одну функцию а именно создать еще одну функцию которая будет использовать 2 этих функции - Это позволить убрать дублирование и именовать исполняемый процесс, сейчас без погружения в конекст не очень понятно что происходит в этом учатске кода

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/init.js#L124

```if (error.isAxiosError) {``` - а если это не parsing, и не axios - что это неизвестная ошибка - в будущем такой подход упростит поиск ошибок.

Если оставить так как есть и сделать ошибку в коде этих функций, 
мы будем видеть что это ошибка сети, хотя это будет ошибка в коде

Определение типа ошибки, достойна отдельной функции

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/init.js#L149-L166

Для закрытия модалки не нужно отдельного обработчика, также не нужно хранить состояние модального окна, с этой задачей справляется сама библиотека boostrap

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/init.js#L9

Имя функции не отражает сути процесса в ней происходящего

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/init.js#L26

Функция не должна ставиться в очередь на повторное исполнение, до того как не закончится выполнение предыдущая

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/getRequest.js#L3

Имя файла не отражает смысл данной функции - нужно думать о доменной области - для чего нужна эта функция

Конструирование url, стоит вынести в отдельную функцию и делать это с помощью ```new URL()```

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/tree/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/renders

Префикс render в именовании каждого файла выглядит излишним, директория уже отражает эту суть

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/renders/renderClosingModal.js

Закрытую модалку никто не видит, нет особого смысла заботиться о ее содержимом

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/renders/renderFeedback.js#L1

Этот блок также нужно конструировать с нуля а не просто изменять его состояние, таких операций как remove точно не должно быть во view

Гибче быть передавать весь state в функцию render, чтобы было понятно контекст откуда берутся эти переменные  text = '', isNotError = true

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/renders/renderForm.js

Конструирование больших блоков html стоит декомпозировать на несколько функции внутри этого файла
таких как buildInput, buildButton

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/renders/renderModal.js#L9

Ид выбранного поста, будет лучше сразу хранить в состоянии

---

https://github.com/aleksandrchusovitin/frontend-project-lvl3/blob/89b3f5644df79b67d6c25e7ace6f7809646489fe/src/renders/renderPosts.js

Тут тоже актуален совет про декомпозицию с разными функция для разных элементов