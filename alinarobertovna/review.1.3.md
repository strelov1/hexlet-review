https://github.com/alinarobertovna/frontend-project-lvl1/blob/e1d1884accfffd8ae06f521b1eca33757436eb4e/src/index.js#L3-L8

К сожалению только переименованием эту проблему из предыдущего ревью не решить
В таких случаях нужно взглянуть на то что делает это функция
1. Выводит приветственный текст
2. Выводит запрос для пользователя о получении его имени
3. Получает его имя и возвращает из функции

Правильное имя этой функции бы звучало вот так:
`greetingAndGetUserName` - прочитав такое имя сразу можно почувстовать [запашок](https://ru.wikipedia.org/wiki/%D0%9A%D0%BE%D0%B4_%D1%81_%D0%B7%D0%B0%D0%BF%D0%B0%D1%88%D0%BA%D0%BE%D0%BC) говорящий о том что с функцией все же чт-то не так, и проблема не с именем. 
В текущем контексте, если мы не будем выделять этот код в функцию, а напишем его сразу в движке по месту использования, у нас только улучшиться читаемость кода. В другом контексте возможно нам пришлось бы разделить эти операции на разные функции


---


https://github.com/alinarobertovna/frontend-project-lvl1/blob/e1d1884accfffd8ae06f521b1eca33757436eb4e/src/utils.js#L1-L4

По сигнатуре функции ожидается что она вернет число в диапазоне от min до max включительно, но на деле это не так

Хотелось бы generateRandomNumber(1, 0) - будет иногда возвращать 1, но это не так, попробуй проверить ее таких вызовом:

```
for (let i=0; i < 1000; i++) {
    if (generateRandomNumber(1, 0) == 1) {
        console.log('bingo!');
    }
}
```

Особенно это критично когда у нас интересует совсем маленький диапазон как здесь, мы никогда не дождемся операции +
https://github.com/alinarobertovna/frontend-project-lvl1/blob/e1d1884accfffd8ae06f521b1eca33757436eb4e/src/games/calc.js#L23


---


https://github.com/alinarobertovna/frontend-project-lvl1/blob/e1d1884accfffd8ae06f521b1eca33757436eb4e/bin/brain-games.js#L3-L5

Похоже здесь использована не та функция, cli.js у нас стал не задействован

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/e1d1884accfffd8ae06f521b1eca33757436eb4e/src/games/gcd.js#L21

Здесь с помощью return мы можем прервать не только цикл, но и функцию, таким образом упростится чтение кода и станет меньше вероятность ошибиться

---

https://github.com/alinarobertovna/frontend-project-lvl1/blob/e1d1884accfffd8ae06f521b1eca33757436eb4e/src/games/progression.js#L25-L27

https://github.com/alinarobertovna/frontend-project-lvl1/blob/e1d1884accfffd8ae06f521b1eca33757436eb4e/src/index.js#L14

Последние два замечания о именовании (figure, task) остались в коде.

Предлагаю подумать об этом так, если прочитать только эти маленькие отрывки кода, можно ли бы по ним в полной мере понять, чем занимается код в конкретном участке?
