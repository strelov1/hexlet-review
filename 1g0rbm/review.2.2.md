Хорошая работа, продолжим делать ее еще лучше.


https://github.com/1g0rbm/frontend-project-lvl2/blob/main/src/formatters/plain.js#L30

path можно формировать с помощью массива, наращивая его в каждой итерации и собирая в строку с помощью join('.')

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/cebdf9b9884bf441216558cc2ce6d333e2f9f6e9/.github/workflows/main.yml#L31-L32

Сейчас при сборке тесты запускаются дважды. Достаточно одного запуска тестов, который выполняется ниже, с генерацией покрытия

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/cebdf9b9884bf441216558cc2ce6d333e2f9f6e9/__tests__/genDiff.test.js#L10-L44

Чтобы не дублировать каждый раз кучу аргументов, можно обернуть вызов path.join в функцию, которая принимает на вход имя файла и возвращает полный путь к фикстуре.

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/cebdf9b9884bf441216558cc2ce6d333e2f9f6e9/__tests__/genDiff.test.js#L10-L44

Также можно значительно уменьшить количество кода в тестах используя test.each. Ведь логика каждого теста одинакова и отличается только набором данных.

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

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/cebdf9b9884bf441216558cc2ce6d333e2f9f6e9/__tests__/formatters/json.test.js#L7-L28

https://github.com/1g0rbm/frontend-project-lvl2/blob/cebdf9b9884bf441216558cc2ce6d333e2f9f6e9/__tests__/formatters/plain.test.js#L7-L21

https://github.com/1g0rbm/frontend-project-lvl2/blob/cebdf9b9884bf441216558cc2ce6d333e2f9f6e9/__tests__/astDiff.test.js#L6-L63

Стоит отделить данные от самих тестов. Используй фикстуры.

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/cebdf9b9884bf441216558cc2ce6d333e2f9f6e9/src/genDiff.js#L14-L15

Судя по имени функция нормализирует путь, но по факту она ещё проверяет существование файла. Это не её зона ответственности.
Проверку на существование файла, будет логично выполнять там где происходит попытка его чтения: в функции getFileData. Так и не нужно будет дважды выполнять проверку и дважды описывать выброс исключения.

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/cebdf9b9884bf441216558cc2ce6d333e2f9f6e9/src/astDiff.js#L17

У объекта ключи всегда строки даже когда мы явно указываем, например числа, поэтому нет необходимости дополнительно выполнять данное преобразование.

Вот например
```
const obj = {
  1: 'value',
};
Object.keys(obj).forEach((el) => {
  console.log(typeof el); // => string
  console.log(el); // => 1
});
```

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/cebdf9b9884bf441216558cc2ce6d333e2f9f6e9/src/astDiff.js#L26-L27

В данном случае достаточно воспользоваться штатными средствами js - firstObj[key].

Использование функции _.get полезно когда нужно получить определённое значение по умолчанию если ключ не найден.

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/cebdf9b9884bf441216558cc2ce6d333e2f9f6e9/src/formatters/plain.js#L27-L38

Вложенное определение. Переопределение данной функции можно вынести на уровень модуля, так как она не зависит от контекста вмещающей функции.

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/cebdf9b9884bf441216558cc2ce6d333e2f9f6e9/src/formatters/stylish.js#L38

Функция iter  возвращает строковое значение, зачем дополнительно выполнять приведение к строке с помощью интерполяции?

---

https://github.com/1g0rbm/frontend-project-lvl2/blob/cebdf9b9884bf441216558cc2ce6d333e2f9f6e9/src/formatters/stylish.js#L3
Не совсем понял идею с sign. В каком случае предполагается использование другого символа.