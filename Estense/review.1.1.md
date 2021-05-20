Добрый день. Андрей! Отличная работа!

Сейчас наступает не менее важная часть разработки - рефакторинг кода. Далее я отправлю список замечаний.
Ваша задача внимательно изучить их и внести исправления в свой код

---

https://github.com/Estense/frontend-project-lvl1/blob/80a7b18af3306c00eca5a686aff281597ac90325/package.json#L5

Это описание попадает в npm репозиторий, разработчикам наткнувшийся на новый пакет было бы приятно если бы из этого описания сразу можно было понять о чем проект

---

https://github.com/Estense/frontend-project-lvl1/blob/80a7b18af3306c00eca5a686aff281597ac90325/makefile

Makefile принято именовать с большой буквы

---

https://github.com/Estense/frontend-project-lvl1/blob/80a7b18af3306c00eca5a686aff281597ac90325/.gitignore#L1

При такой записи будут игнорироваться как файлы с именем node_modules, так и директории с таким же именем. У нас задача игнорировать директорию node_modules в корне проекта.

Изучите таблицу паттернов по .gitignore и внесите необходимые изменения https://www.atlassian.com/git/tutorials/saving-changes/gitignore

---

https://github.com/Estense/frontend-project-lvl1/blob/80a7b18af3306c00eca5a686aff281597ac90325/src/games/brain-calc.js#L2

Функции это всегда глаголы, подобробнее о хорошем наименование можно почитать [здесь](https://ru.hexlet.io/blog/posts/naming-errors-1)

Старайтесь делать наименование функции, такое чтобы ее назначение было ясно без погружения в контекст всей программы

---

https://github.com/Estense/frontend-project-lvl1/blob/80a7b18af3306c00eca5a686aff281597ac90325/src/index.js#L10

Использование магических чисел, подробнее [здесь](https://ru.hexlet.io/blog/posts/magic-numbers)

---

https://github.com/Estense/frontend-project-lvl1/blob/80a7b18af3306c00eca5a686aff281597ac90325/src/index.js#L8

Переменная с `s` на конце, подразумевает о том что в ней будет храниться коллекция, в данном примере, хранится не коллекция а описание, нужно присвоить имя этой переменной, так чтобы по нему было понятно содержание этой переменной

---

https://github.com/Estense/frontend-project-lvl1/blob/80a7b18af3306c00eca5a686aff281597ac90325/src/index.js#L17

https://github.com/Estense/frontend-project-lvl1/blob/80a7b18af3306c00eca5a686aff281597ac90325/src/index.js#L20

Подумайте, есть ли смысл возвращать результат вызова функции conosle.log из движка. Функции согласно принципу CQS являются либо командой, которая выполняет действие (action), либо запросом (query), который извлекает данные, но не тем и другим одновременно. В данном случае движок является командой и ему нечего возвращать. Поэтому тут просто нужно вызвать функцию и прервать работу движка используя return;.

---

https://github.com/Estense/frontend-project-lvl1/blob/80a7b18af3306c00eca5a686aff281597ac90325/src/games/brain-calc.js#L10

В переменной хранится не рандомное число, о чем можно подумать прочитав это имя

---

https://github.com/Estense/frontend-project-lvl1/blob/80a7b18af3306c00eca5a686aff281597ac90325/src/games/brain-calc.js#L22-L23

Здесь не обязательно сохранять массив в переменную перез его возрастом, можно вернуть сразу массив

---

https://github.com/Estense/frontend-project-lvl1/blob/80a7b18af3306c00eca5a686aff281597ac90325/src/games/brain-calc.js#L19-L20

Нужно добавить возврат исключений в дефолтное поведение, подробнее можно почитать здесь https://ru.hexlet.io/blog/posts/sovershennyy-kod-defolty-v-svitchah, сейчас если в переменной randomSymbol будет неизвестный оператор, то функция вернет просто undefiend,
такой результат может привести к неожиданному поведению и часам отладки, на то чтобы это обнаружить

---

https://github.com/Estense/frontend-project-lvl1/blob/80a7b18af3306c00eca5a686aff281597ac90325/src/games/brain-calc.js#L7-L12

Если в будущем у нас добавится еще один оператор например деление, не сломает ли это наш код? Подумайте о том как можно сделать чтобы в будущем не пришлось менять диапазон для рандомных значений

---

https://github.com/Estense/frontend-project-lvl1/blob/80a7b18af3306c00eca5a686aff281597ac90325/src/games/brain-calc.js#L12-L21

Этот код отличный кандидат для выделения его в отдельную функцию

---

https://github.com/Estense/frontend-project-lvl1/blob/80a7b18af3306c00eca5a686aff281597ac90325/src/games/brain-progression.js#L6-L20

Код данной функции будет понятнее если его разделить на функции, 1 создает прогрессию, 2 скрывает элемент и получает правильный ответ

---

Многие замечания выше, особенно это именование переменных, и выделения кода в отдельные функции, подходят не только к конкретным примерам выше, перед отправкой на следующей проверку рекомендую проверить весь код на соответвуие этим рекомендациям.

---

Все вопросы, которые возникают, задавайте мне в слаке. Там мы их сможем оперативно решить.
