
https://github.com/eyt5297/frontend-project-lvl2/blob/a942b1147b34f431711eec67b7006b54e38066d7/src/formatters/plain.js#L17-L38

Здесь переменная res не к чему, можно сразу возвращать 

```return currentValue.filter...```


_________________

https://github.com/eyt5297/frontend-project-lvl2/blob/a942b1147b34f431711eec67b7006b54e38066d7/src/index.js#L12-L36

Аналогично предыдущему комментарию

_________________


https://github.com/eyt5297/frontend-project-lvl2/blob/a942b1147b34f431711eec67b7006b54e38066d7/src/parsers.js#L12

Здесь в ошибке было бы неплохо вывести что именно за формат туда пришел, это упростит дальнейшую отладку в случае возникнования ошибки


_________________

https://github.com/eyt5297/frontend-project-lvl2/blob/a942b1147b34f431711eec67b7006b54e38066d7/src/formatters/stylish.js#L17

Символ пробела имеет смысл внести в константу, для того чтобы была возможность его подменить

Само выражение, имеет смысл также именовать с помощью переменной (например closeOffset), чтобы было понятно что за действия там происходят 

```${'  '.repeat(shiftCount - 1)}```

_________________

https://github.com/eyt5297/frontend-project-lvl2/blob/a942b1147b34f431711eec67b7006b54e38066d7/src/formatters/stylish.js#L20

Имя функции stylish выглядит тут выглядит уместнее

_________________

https://github.com/eyt5297/frontend-project-lvl2/blob/a942b1147b34f431711eec67b7006b54e38066d7/src/formatters/stylish.js#L5

https://github.com/eyt5297/frontend-project-lvl2/blob/a942b1147b34f431711eec67b7006b54e38066d7/src/formatters/plain.js#L3

А здесь stringify - общепринятый вариант наименования подобных функций
_________________

https://github.com/eyt5297/frontend-project-lvl2/blob/a942b1147b34f431711eec67b7006b54e38066d7/src/formatters/stylish.js#L23

https://github.com/eyt5297/frontend-project-lvl2/blob/a942b1147b34f431711eec67b7006b54e38066d7/src/formatters/stylish.js#L9

Магические числа, подробнее о них https://ru.hexlet.io/blog/posts/magic-numbers
