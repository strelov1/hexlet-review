
Добрый день. Игорь! Отличная работа! 

Вижу что отлично усвоил пройденное в первом проекте.

Теперь самое время сделать работу еще лучше :)

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/4c02acf9fa7e385c28a49e08ec83ca5aae772f25/src/parsers.js#L5

здесь можно упростить до

```
yaml: jsYaml.load
```

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/4c02acf9fa7e385c28a49e08ec83ca5aae772f25/src/file.js#L7-L9

Неявный код, проще и понятнее было дополнить словарь здесь
https://github.com/1g0rbm/frontend-project-lvl2/blob/4c02acf9fa7e385c28a49e08ec83ca5aae772f25/src/parsers.js#L5

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/4c02acf9fa7e385c28a49e08ec83ca5aae772f25/src/genDiff.js#L10

Можно упростить интерфейс этой функции

getParser(content, format);

Имя функции в таком случае должно измениться, в соответствии с процессом

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/4c02acf9fa7e385c28a49e08ec83ca5aae772f25/src/genDiff.js#L24

Имя функции render, не соответствует ее назначение, функция ничего не отрисовывает, а только изменяет формат представляения

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/4c02acf9fa7e385c28a49e08ec83ca5aae772f25/src/genDiff.js#L4

В таких случае в названии лучше бы смотрелось что-то вроде buildAst, create,make и т.д. - потому что мы его не получаем а строим


---

https://github.com/1g0rbm/frontend-project-lvl2/blob/4c02acf9fa7e385c28a49e08ec83ca5aae772f25/src/astDiff.js#L51

На вход приходят объекты а деверво у нас на выходе


---

https://github.com/1g0rbm/frontend-project-lvl2/blob/4c02acf9fa7e385c28a49e08ec83ca5aae772f25/src/astDiff.js#L3-L32

Идея очень правильная, изолируем работу с ast через функции, но в данном случае больше похоже оверинижинирнг, мы знаем структуру дерева, а такие функции к сожалению не упрощают чтение кода, приходится постоянно обращаться в файл с объевлением дерева и смотреть что эти функции делают

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/4c02acf9fa7e385c28a49e08ec83ca5aae772f25/src/astDiff.js#L49

Под условие isObject могут попасть также массивы, для этого лучше подходит isPlainObject

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/4c02acf9fa7e385c28a49e08ec83ca5aae772f25/src/astDiff.js#L72

Если сравнить два одинаковые объекта таким способом, то всегда получим false в этом условии, в lodash есть подходящая функция для этой цели

---


https://github.com/1g0rbm/frontend-project-lvl2/blob/4c02acf9fa7e385c28a49e08ec83ca5aae772f25/src/astDiff.js#L65-L69

value это просто данные, в случае передачи вложенного ast нужно класть его в соответствующую структуру
children, благодаря такому подходу будет код будет иметь более ожидаемое поведение и лучше читаться
