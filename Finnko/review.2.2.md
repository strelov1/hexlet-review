https://github.com/Finnko/frontend-project-lvl2/blob/e3da89498e21e83b3588524e7e4acf43b26c680a/package.json#L4

Описание не появилось :-(

---

https://github.com/Finnko/frontend-project-lvl2/blob/e3da89498e21e83b3588524e7e4acf43b26c680a/.github/workflows/tests-check.yml#L21-L28

Тесты запускаются 2 раза

Можно убрать
```
make test
```

---

https://github.com/Finnko/frontend-project-lvl2/blob/e3da89498e21e83b3588524e7e4acf43b26c680a/src/parser.js#L10-L11

Нужно обработать исключение - если придет неизвестный формат - выбросить ошибку

---

https://github.com/Finnko/frontend-project-lvl2/blob/e3da89498e21e83b3588524e7e4acf43b26c680a/src/formatters/index.js#L6

Вот тут не требуется значения по умолчанию

---

https://github.com/Finnko/frontend-project-lvl2/blob/e3da89498e21e83b3588524e7e4acf43b26c680a/src/formatters/plain.js#L16-L22

Не совсем так, проверка path.length > 0 не имеет смысла, выделять в функцию тоже нет смысла

```
const keys = [...path, key];
const attrName = keys.join('.')
```

---

https://github.com/Finnko/frontend-project-lvl2/blob/e3da89498e21e83b3588524e7e4acf43b26c680a/src/formatters/stylish.js#L36

https://github.com/Finnko/frontend-project-lvl2/blob/e3da89498e21e83b3588524e7e4acf43b26c680a/src/formatters/stylish.js#L14

Из предыдущего ревью, мало что поменялось в этом смысле

```
У нас вроде уже есть записанная константа SPACE_COUNT, но повсюду используется магические числа https://ru.hexlet.io/blog/posts/magic-numbers
А переносы строк \n лучше вынести как разделитель при join

styledDiff.join('\n')
```

---

https://github.com/Finnko/frontend-project-lvl2/blob/e3da89498e21e83b3588524e7e4acf43b26c680a/src/formatters/stylish.js#L21

Не забываем про переносы строк