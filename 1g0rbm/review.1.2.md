Игорь, день добрый!

Вы хорошо отрефакторили проект, логика значительно упростилась и кода стало ещё меньше, что очень хорошо. Продолжим работу над вашим проектом.

https://github.com/1g0rbm/frontend-project-lvl1/blob/e4e86e7c70f6e00fb4ae443ff9d12e5074dc1935/bin/brain-calc.js#L5

Функции глаголы, какой процесс выполняет эта функция?, если перевести его на английский - это будет отличное название функции

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/e4e86e7c70f6e00fb4ae443ff9d12e5074dc1935/src/games/brain-calc.js#L14

Здесь у нас появились магические числа, в данном контексте приемлемо использовать литералы самих символов, если хочется использовать константы то тогда нужно было создать для каждого символа, из этими константами наполнить масив OPERATIONS,

В тайпскрипте есть решение лучше https://www.typescriptlang.org/docs/handbook/enums.html
но это пока рано)

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/e4e86e7c70f6e00fb4ae443ff9d12e5074dc1935/src/games/brain-progression.js#L7

Функция генерации прогрессии лучше оставить чистой, а начальное значение передать ей аргументом

Прогрессию стоит всю в цикле собирать. И не разделять эту операции на части с инициализацией

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/e4e86e7c70f6e00fb4ae443ff9d12e5074dc1935/src/index.js#L3

Имя переменной должно быть STEPS_COUNT
Подробнее о именовании (#Количество) https://ru.hexlet.io/blog/posts/naming-in-programming

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/e4e86e7c70f6e00fb4ae443ff9d12e5074dc1935/src/index.js#L5

gameQuestion - не очень подходящие имя для этой переменной, так как это не вопрос а описание игры, вопрос есть ниже

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/e4e86e7c70f6e00fb4ae443ff9d12e5074dc1935/src/games/brain-progression.js#L22-L23

Лучше избежать мутирования, и выделить эту операцию в отдельную функцию, которая примет прогрессию и вернет новую с заменнным значением
