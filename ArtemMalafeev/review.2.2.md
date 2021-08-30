Добрый день. Артем! Уже намного лучше, но есть еще места где можно сделать лучше

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/5e0d8ab61c74872c092283ef5442da7052c97c3f/src/formatters/plain.js#L15

Имя переменной осталось status, это вводит в заблуждение, имеет смысл передавать в эту функцию путь и саму ноду

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/5e0d8ab61c74872c092283ef5442da7052c97c3f/src/formatters/plain.js#L48

Можно было бы отфильтровать по типу unchanged выше, это упростило код в функции format и условие фильтрации было бы яснее

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/5e0d8ab61c74872c092283ef5442da7052c97c3f/src/formatters/stylish.js#L7

Можно использовать `Object.entries(value).map(([key, value]) => {})` - это позволит итерировать сразу по ключу и значению

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/5e0d8ab61c74872c092283ef5442da7052c97c3f/src/formatters/stylish.js#L8-L14

Все же текущий отступ и закрывающий нужно рассчитать отдельно, чтобы не писать пробелы ````${indent}    ${key}:```, если мы изменим наполнитель или размер отступа то придется многое переписывать

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/5e0d8ab61c74872c092283ef5442da7052c97c3f/src/formatters/stylish.js#L3

Заполняющие символы (пробел) нужно вынести в константы, и размеры отступов также

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/5e0d8ab61c74872c092283ef5442da7052c97c3f/src/formatters/plain.js#L33

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/5e0d8ab61c74872c092283ef5442da7052c97c3f/src/formatters/stylish.js#L50

Не хватает проверки на несуществующий тип

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/5e0d8ab61c74872c092283ef5442da7052c97c3f/src/formatters/stylish.js#L14

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/5e0d8ab61c74872c092283ef5442da7052c97c3f/src/formatters/stylish.js#L73

Формирование строк удобнее формировать с помощью join
```
['{', ...lines, closeIdent, '}'].join('\n')
```

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/5e0d8ab61c74872c092283ef5442da7052c97c3f/src/genAST.js

название функции buildAST, отлично бы подошла и к наименованию файла

_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/5e0d8ab61c74872c092283ef5442da7052c97c3f/src/genAST.js#L3

Не стоит усложнять именования числами, в данном контексте obj1, obj2 отлично отражают суть


_________________

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/5e0d8ab61c74872c092283ef5442da7052c97c3f/__tests__/genDiff.test.js#L16-L28


Можно уменьшить количество кода в тестах используя test.each. Ведь логика каждого теста одинакова и отличается только набором данных.

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

https://github.com/ArtemMalafeev/frontend-project-lvl2/blob/5e0d8ab61c74872c092283ef5442da7052c97c3f/__tests__/genDiff.test.js#L13-L14

Саму функцию для получения файла можно отделить, а вот ее вызов лучше поместить в блоке перед expect