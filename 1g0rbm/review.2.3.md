https://github.com/1g0rbm/frontend-project-lvl2/blob/f3f006d71c86d2c3fd0bace2bf61c607016363ee/src/astDiff.js#L16

Нужен ли здесь в конце map?

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/f3f006d71c86d2c3fd0bace2bf61c607016363ee/__tests__/genDiff.test.js#L14-L17

Меньше кода и меньше вероятности ошибиться, если формировать массив в константными значениями
а потом эти значения разворачивать в теле теста перед expect

```
{
  filepath1: 'file1.json',
  filepath2: 'file2.json',
  format: 'stylish',
  expected: 'resultStylish.txt'
},
```

---


https://github.com/1g0rbm/frontend-project-lvl2/blob/f3f006d71c86d2c3fd0bace2bf61c607016363ee/__tests__/genDiff.test.js#L17

Имеет смысл завести heleper для получения данных