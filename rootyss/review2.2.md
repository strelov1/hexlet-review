https://github.com/rootyss/frontend-project-lvl2/blob/b6117d79517b55d17372b8fc91ee9bf810da096d/src/parser.js#L12-L20

У функции парсера у нас по прежнему осталось слишком много обязанностей, нужно превратить эту функцию в [фабрику ](https://github.com/Hexlet/patterns/tree/master/content/factory)и возвращающую саму функцию парсера JSON.parse или yaml.load в зависимости от переданного ей формата

с получение функцию форматирование у нас по сути была аналогичная ситуация (это правильный вариант) https://github.com/rootyss/frontend-project-lvl2/blob/b6117d79517b55d17372b8fc91ee9bf810da096d/src/formatters/index.js

_________________

https://github.com/rootyss/frontend-project-lvl2/blob/b6117d79517b55d17372b8fc91ee9bf810da096d/src/parser.js#L6-L10

Целесообразность данных функции сомнительная
_________________

https://github.com/rootyss/frontend-project-lvl2/blob/b6117d79517b55d17372b8fc91ee9bf810da096d/src/getObjDifference.js#L28-L29

Даже если объекты будут одинаковы, данная проверка всегда будет возвращать true. Сравнение корректней будет производить с помощью функции isEqual в lodash
_________________

https://github.com/rootyss/frontend-project-lvl2/blob/main/src/getObjDifference.js#L21

Рекурсивная проверка должна быть только когда обе ноды объекты, но не массивы https://lodash.com/docs/4.17.15#isPlainObject

_________________

https://github.com/rootyss/frontend-project-lvl2/blob/b6117d79517b55d17372b8fc91ee9bf810da096d/src/formatters/plain.js#L15

!(el.type === 'identical')  в данном случае проще использовать el.type !== 'identical'

С помощью операторов распаковки конструкцию можно упрощать до такого выражения
```
data.filter(({type}) => type !== 'identical')
```

_________________

https://github.com/rootyss/frontend-project-lvl2/blob/b6117d79517b55d17372b8fc91ee9bf810da096d/src/formatters/stylish.js#L42

Хороший подход упрощающий отладку, вывести не походящие значение в ошибке
```
throw new Error(`Unknown type: ${type}`);
```