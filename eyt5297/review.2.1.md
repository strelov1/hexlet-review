Добрый день. Евгений! Отличная работа! 

Сейчас наступает не менее важная часть разработки - рефакторинг кода. Далее я отправлю список замечаний.
Твоя задача внимательно изучить их и внести исправления в свой код


https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/README.md

Бейдж codeclimate ссылается на тестовый репозиторий хекслета

Бейдж автопроверок хекслета ведет на 404 ошибку, сама картинка с беджеом также поломана

Не хватает инструкций по первичной установки проекта и asciinema c примерами запуска

_________________

https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/src/cli.js#L1-L4

Можно упростить до

```
import { program } from 'commander';
```

_________________

https://github.com/eyt5297/frontend-project-lvl2/tree/7b426f8eee89cd5fc090761f21fd16420ae85539/data

Для этих файлов уже есть отличное место - директория ```__fixtures__```

_________________


https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/src/index.js#L2

Функции это всегда глаголы, подобробнее о хорошем наименование можно почитать [здесь ](https://ru.hexlet.io/blog/posts/naming-errors-1)

_________________

https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/src/parsers.js#L10-L21

Функция parseFile делает слишком много действий тем самым нарушает принцип [CQRS](https://ru.wikipedia.org/wiki/CQRS).

В ней происходит загрузка файла, определение формата, и парсинг - все кроме последнего - не ответственность этой функции

Также нужно не забыть о обработке ошибок в случае если пользователь передаст не поддерживаемый формат файла

_________________


https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/src/index.js#L11

includes довольно сложная проверка, по сути там происходит итерация по всем ключам и сравнение их с переданным ключом,
мы можем упростить такую проверку, зная что obj1, obj2 это объекты (они же хэш таблицы) мы можем проверить наличие ключа за операцию O(1) 

```
_.has(obj1, key);
```
_________________

https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/src/index.js#L26

Сравнение двух одинаковых объектов или массивов всегда будет возвращать false, хоть мы и знаем что условие выше нам не пропустит к этому сравнению двух объектов - корректней будет использовать isEqual из lodash

_________________


https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/src/formatters/index.js#L12

Осталась отладочная печать

_________________

https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/src/formatters/index.js#L13

Не хватает проверки, поддерживается ли определенный форматер

_________________

https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/src/formatters/plain.js#L22

Здесь слегка усложнено, сначала склеивается в строчку, потом оборачивается в массив для следующей итерации
Было бы проще если завести две переменных, одна собирающая путь с последующей передачей его в следующую итерацию, а вторая склеивающая путь с точками и используямая при ввыоде

_________________

https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/src/formatters/plain.js#L12

Приведение к строки лучше делать явно String(value), но в данном случае это не требуется делать вообще

_________________


https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/src/formatters/plain.js#L32-L33

default в свитчах необходимо обрабатывать по особому, подробнее можно почитать [здесь](https://ru.hexlet.io/blog/posts/sovershennyy-kod-defolty-v-svitchah)

_________________

https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/src/formatters/plain.js#L35

Такого кейса не должно быть при условии если default обработан корректно

_________________

https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/src/formatters/stylish.js#L33

Тип node не очень удачное название, так как они все node, лучше бы подошло nested

_________________


https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/src/formatters/stylish.js#L8-L9

Удобнее здесь итерировать с помощью Object.entries

_________________


https://github.com/eyt5297/frontend-project-lvl2/blob/7b426f8eee89cd5fc090761f21fd16420ae85539/__tests__/index.test.js

Можно значительно уменьшить количество кода в тестах используя test.each. Ведь логика каждого теста одинакова и отличается только набором данных.

https://jestjs.io/docs/en/api#testeachtablename-fn-timeout

```
test.each([
  [1, 1, 2],
  [1, 2, 3],
  [2, 1, 3],
])('.add(%i, %i)', (a, b, expected) => {
  expect(a + b).toBe(expected);
});
```

_________________



Все вопросы, которые возникают, задавай мне в слаке. Там мы их сможем оперативно решить.
