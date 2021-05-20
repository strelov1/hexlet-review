Добрый день. Артем! Отличная работа!

С первой попытки и так близко к идеалу!

Сейчас наступает не менее важная часть разработки - рефакторинг кода. Далее я отправлю список замечаний.
Ваша задача внимательно изучить их и внести исправления в свой код

---

https://github.com/ArtemMalafeev/frontend-project-lvl1/blob/b3c3863156e4cbe0dec8fec0dbf4c711537acf64/package.json#L4

Это описание попадает в npm репозиторий, разработчикам наткнувшийся на новый пакет было бы приятно если бы из этого описания сразу можно было понять о чем проект

---

https://github.com/ArtemMalafeev/frontend-project-lvl1/blob/b3c3863156e4cbe0dec8fec0dbf4c711537acf64/bin/brain-calc.js#L5

Функции это всегда глаголы, подобробнее о хорошем наименование можно почитать [здесь](https://ru.hexlet.io/blog/posts/naming-errors-1)

Старайтесь делать наименование функции, такое чтобы ее назначение было ясно без погружения в контекст всей программы

---

https://github.com/ArtemMalafeev/frontend-project-lvl1/tree/b3c3863156e4cbe0dec8fec0dbf4c711537acf64/games

Директория games является часть исходного кода и должна находится в директории src

---

https://github.com/ArtemMalafeev/frontend-project-lvl1/blob/b3c3863156e4cbe0dec8fec0dbf4c711537acf64/src/index.js#L10

Лучше поднять эту константу на уровне модуля. При необходимости её можно будет экспортировать из модуля и использовать там где это нужно. Также это позволит протестировать её значение

---

https://github.com/ArtemMalafeev/frontend-project-lvl1/blob/b3c3863156e4cbe0dec8fec0dbf4c711537acf64/src/index.js#L18

https://github.com/ArtemMalafeev/frontend-project-lvl1/blob/b3c3863156e4cbe0dec8fec0dbf4c711537acf64/games/calc.js#L6

Функции всегда глаголы, см. выше

---

https://github.com/ArtemMalafeev/frontend-project-lvl1/blob/b3c3863156e4cbe0dec8fec0dbf4c711537acf64/games/calc.js#L5

Здесь глагол, но без погружения в контекст сложновато понять что функция делает

---

https://github.com/ArtemMalafeev/frontend-project-lvl1/blob/b3c3863156e4cbe0dec8fec0dbf4c711537acf64/src/getRandom.js

Семантичнее сделать параметр min обязательным и поменять его местами,такая сигнатура функции будет более привычная так как такой же подход используется в стандартных библиотеках https://www.php.net/manual/en/function.random-int.php, https://www.w3schools.com/python/ref_random_randint.asp.

Код использующий эту функцию также не должен завязывать на значения по умолчанию, так как если это значения поменяется, код ее использующий может сломаться.

Также поведение этой функции было бы более ожидаемым если бы оно возвращало число в диапазоне от min до max включительно.

Ожидается что randomNumber(1, 0) - будет иногда возвращать 1, но это не так, попробуй проверить ее таких вызовом:

```
for (let i=0; i < 1000; i++) {
    if (randomNumber(1, 0) == 1) {
        console.log('bingo!');
    }
}
```

---

https://github.com/ArtemMalafeev/frontend-project-lvl1/blob/b3c3863156e4cbe0dec8fec0dbf4c711537acf64/games/calc.js#L19

В данном случае нужно поднимать (throw) ошибку, а не возвращать ее текст, так как в данном случае, придется обрабатывать этот текст на уровне выше, подробнее можно почитать [здесь](https://ru.hexlet.io/blog/posts/sovershennyy-kod-defolty-v-svitchah)

---

https://github.com/ArtemMalafeev/frontend-project-lvl1/blob/b3c3863156e4cbe0dec8fec0dbf4c711537acf64/games/calc.js#L26

В целом идея с использованием @hexlet/pairs может и выглядит привлекательным, но в данном случае это немного злоупотребление, у нас уже появилась функция calculate, которая должна знать о том что operands это особая структура данных, это само по себе не всегда плохо, но в конкретном примере выглядит излишне

---

https://github.com/ArtemMalafeev/frontend-project-lvl1/blob/b3c3863156e4cbe0dec8fec0dbf4c711537acf64/games/progression.js#L40

https://github.com/ArtemMalafeev/frontend-project-lvl1/blob/b3c3863156e4cbe0dec8fec0dbf4c711537acf64/games/progression.js#L43

А если длину прогрессии уменьшить, не сломает ли это наш код?

---

Все вопросы, которые возникают, задавайте мне в слаке. Там мы их сможем оперативно решить.
