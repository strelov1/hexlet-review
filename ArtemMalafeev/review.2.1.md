Добрый день. Артем! Отличная работа!

Сейчас наступает не менее важная часть разработки - рефакторинг кода. Далее я отправлю список замечаний.
Твоя задача внимательно изучить их и внести исправления в свой код

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/.github/workflows/node.js.yml#L33-L35


Прогон этого теста избыточен, так как ниже в make test-coverage проводятся те же тесты

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/.DS_Store

Такие файлы не нужно хранить в репозитории, его следует удалить, и добавить в .gitignore чтобы в будущем он не добавлялся

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/tree/87ba03ac33fa746b7702401ca64fa63822cad4d1/src

В директорию src необходимо добавить index.js файл экспортирующий genDiff из директории, так мы будем видеть начальную точку входа в этой директории

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/src/file.js

Название вводим в заблуждение, лучше бы подошло просто utils.js, ну если хочется акцентировать на том что здесь строго утилиты для работы с файлами то file-utils.js

_________________


https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/src/file.js#L19-L22

Слишком много ответственности для одной функции, стоит разделить их на две простые

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/src/file.js#L4-L16

Здесь производится лишняя работы, такого поведения что программа будет пытаться находить сначала относительные пути потом абсолютные от программы никто не ожидает, это ответсвенность того кто передает аргументы.
Посмотри на то какие аргументы принимает стандартная программа `cat` в каком виде ей можно передавать пути - такой же интерфейс ожидается и для gendiff

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/src/genAST.js#L5

На вход приходит 2 объекта - дерево мы получаем на выходе - это об именовании переменных

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/src/genAST.js#L6

```
_.union(_.keys(obj1), _.keys(obj2))
```

Так смотрелось бы лучше

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/src/genAST.js#L3

Какой смысл в этой функции, легче читалось бы

```
return { key, value: _.get(tree2, key), status: 'added' }
```

_.get(tree2, key) - здесь избыточен, его использует для удобного определения по умолчанию, в данном случаю он здесь не используется - `tree2[key]`

status - ну удачное имя для переменной - оно отражает состояние ноды, у нас такого нет - зато есть тип

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/src/genAST.js#L21

Под условие isObject могут попасть также массивы, для этого лучше подходит isPlainObject

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/src/genAST.js#L22

Имя object - не очень удачное в данном контексте, nested хорошо бы объясняло смысл работы этой ноды

В nested ноде должна быть другая структура с children - отражающая смысл содержания

_________________

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8df188f7df2e371bb1a4ac529c5b2ebc6fa068ce/src/buildTree.js#L23

Даже если объекты будут разные, данная проверка всегда будет возвращать false. Сравнение корректней будет производить с помощью функции isEqual в lodash


_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/src/parsers.js#L15

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/src/formatters/index.js#L18

Про _.get писал выше

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/src/formatters/plain.js#L3

Каноническое имя для таких функций - stringify

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/src/formatters/plain.js#L11

render - смысл отрисовывать, в нашем случае мы форматируем - format

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/87ba03ac33fa746b7702401ca64fa63822cad4d1/src/formatters/plain.js#L8

Тернарный оператор в большинстве случаев ухудшает читаемость, if со своей веткой тут бы смотрелся лучше

_________________

Все вопросы, которые возникают, задавай мне в слаке. Там мы их сможем оперативно решить.
