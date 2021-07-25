
https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8030431ed7a2f4e9e474ade192eb2b38e19a7f98/src/index.js#L8

Получение расширения файла лучше выделить в отдельную функцию, благодаря этому мы уберем дублирование кода, и куда более важное с помощью имени функции объясним суть происходящего

---

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8030431ed7a2f4e9e474ade192eb2b38e19a7f98/src/formatters/formatPlain.js#L13-L15

Распаковку объекта можно было бы сделать в агрументе map

```
map(({ key, type, value, oldValue, newValue, children})
```

---

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8030431ed7a2f4e9e474ade192eb2b38e19a7f98/src/formatters/formatPlain.js#L16

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8030431ed7a2f4e9e474ade192eb2b38e19a7f98/src/formatters/formatPlain.js#L25

Дважды создается один и тот же массив, переменную хращаяую уже собранное значение лучше стоит отделить от сбора массива. newPath - не самое удачное имя для переменной, подумай что хранить этот массив `[...path, key]`
Вообще приставка new, this - это верный признак переменной над именований, которой подумали недостаточно

---

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8030431ed7a2f4e9e474ade192eb2b38e19a7f98/src/formatters/formatPlain.js#L6

Приведение к строке лучше делать явно, интерполяция строк нужна именно для склеивание двух и более элементов в строку

---

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8030431ed7a2f4e9e474ade192eb2b38e19a7f98/src/formatters/formatStylish.js#L6

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8030431ed7a2f4e9e474ade192eb2b38e19a7f98/src/formatters/formatStylish.js#L12

Надежнее будет использовать библиотеку lodash для таких случаев

---

https://github.com/aleksandrchusovitin/frontend-project-lvl2/blob/8030431ed7a2f4e9e474ade192eb2b38e19a7f98/src/formatters/formatStylish.js#L13

Часть магических чисел все же осталось, у нас есть 2 вида отступов, и все остальные вычисляются из этих 2х значений