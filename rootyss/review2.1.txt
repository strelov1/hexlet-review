Владимир - отличная работа!

Вижу что вы отлично усвоили пройденное в первом проекте.

Теперь самое время сделать работу еще лучше :)
_________________

https://github.com/rootyss/frontend-project-lvl2/blob/main/.github/workflows/nodeCI.yml#L32-L33

В нашем случае сборки не происходит, нужно подправить описание

_________________

https://github.com/rootyss/frontend-project-lvl2/blob/main/src/parser.js#L6-L14

Данная функция делает не только парсинг файла, о чем можно подумать исходя из ее названия
она - находит полным путь к файлу, получает содержимое файла, и только потом уже производит парсинг содержимого
Напомню имя функции всегда глагол которые ее описывает, в данном случае функция должна была бы называться примерно так 
(findFullPathReadFileParse) - такое название намекает что с функцией что-то не так и что у нее слишком много обязанностей

https://github.com/rootyss/frontend-project-lvl2/blob/main/src/index.js#L5

Функция genDiff является основным процессом, и она может себе позволить делать множество обязанностей

_________________

https://github.com/rootyss/frontend-project-lvl2/blob/main/src/index.js#L9-L50

Стоило бы вынести объявление данной функции из основного потока - и даже файла, и дать ей хорошее название описывающие ее работу

_________________


https://github.com/rootyss/frontend-project-lvl2/blob/main/src/formatters/plain.js#L16

Строки конкатенировать лучше через интерполяцию `${name}${elem.name}`

_________________

https://github.com/rootyss/frontend-project-lvl2/blob/main/src/formatters/plain.js#L31

Может ли у нас быть нода без типа? если да не является ли это ошибкой?

_________________

https://github.com/rootyss/frontend-project-lvl2/blob/main/src/formatters/plain.js#L33

Ноду с типом identical стоило отфильтровать предварительно перед основной итерацией,
в таком случае не пришлось бы писать не явный код с null и его последующей фильтрацией

_________________

https://github.com/rootyss/frontend-project-lvl2/blob/main/src/formatters/plain.js#L18-L30

Конструкция switch здесь бы смотрелась органично