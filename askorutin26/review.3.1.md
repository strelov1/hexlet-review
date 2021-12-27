Поздравляю с завершение проекта

Очень аккуратный код, приятно смотреть.


https://github.com/askorutin26/frontend-project-lvl3/blob/2cde0cf795b1001236fbae6ed890b179864763ca/README.md

Не хватает инструкции для установки и использованию, а также описания проекта

---

https://github.com/askorutin26/frontend-project-lvl3/blob/2cde0cf795b1001236fbae6ed890b179864763ca/src/i18n.js#L5-L18

Такой способ все же будет не корректным объявлением, мы здесь создаем таким сопсобом глобальную переменную и такой код не будет нам гарантировать корректную подгрузку перевода, сейчас она корректна только потому что список слов не такой большой, то рендер бы у нас успел сработать до загрузки перевода. Нужно перенести инициализацию i18n app и весь код в app должен объявляться уже в отрезолвленном i18n 


---

https://github.com/askorutin26/frontend-project-lvl3/blob/2cde0cf795b1001236fbae6ed890b179864763ca/src/urlValidator.js#L4-L6

Так не стоит делать, валидаторов может стать больше, их и сейчас больше `string(), required()` - а ошибки всего 2

Константы для ошибок можно определить через

`yup.setLocale(locale);`

---

https://github.com/askorutin26/frontend-project-lvl3/blob/2cde0cf795b1001236fbae6ed890b179864763ca/src/urlValidator.js#L13

В нашем случае правильнее будет использовать асинхронную функцию `validate`


---

https://github.com/askorutin26/frontend-project-lvl3/blob/2cde0cf795b1001236fbae6ed890b179864763ca/src/rssParser.js#L5

Данный возврат усложняет обработку этой функции извне, правильнее будет выбросить исключение

---

https://github.com/askorutin26/frontend-project-lvl3/blob/2cde0cf795b1001236fbae6ed890b179864763ca/src/watcher.js#L20

Почему массив?

---

https://github.com/askorutin26/frontend-project-lvl3/blob/2cde0cf795b1001236fbae6ed890b179864763ca/src/watcher.js#L43

https://github.com/askorutin26/frontend-project-lvl3/blob/2cde0cf795b1001236fbae6ed890b179864763ca/src/watcher.js#L48

Можно обойтись без перенавешивания обработчиков если мы:
1) Положим в dom в data атрибут ид поста
https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/dataset

2) Обработчик будет вешать не на сами кнопки а на весь див с постами, а при обработки клика будет определять если нужный нам дата атрибут в таргете - если есть загружать его в стейт

---

https://github.com/askorutin26/frontend-project-lvl3/blob/2cde0cf795b1001236fbae6ed890b179864763ca/src/handler.js#L107-L121

Не нашел использования

---

https://github.com/askorutin26/frontend-project-lvl3/blob/2cde0cf795b1001236fbae6ed890b179864763ca/src/view.js#L244-L248

вместо filter()[0] можно использовать функцию find() она сразу вернет нам нужный элемент

---

https://github.com/askorutin26/frontend-project-lvl3/blob/2cde0cf795b1001236fbae6ed890b179864763ca/src/view.js#L241-L252

Очень сложное извлечение, достаточно просто

```
const post = state.posts.find(({ id }) => id === state.modal.postId);
```

Сохранить state.modal.postId с помощью data атрибута, описал выше

---

https://github.com/askorutin26/frontend-project-lvl3/blob/2cde0cf795b1001236fbae6ed890b179864763ca/src/view.js#L46

Подобный конструкции удобнее создавать динамически

```i18next.t(`validation.${state.formState.validationResult}`)```

---

https://github.com/askorutin26/frontend-project-lvl3/blob/2cde0cf795b1001236fbae6ed890b179864763ca/src/watcher.js#L14-L16

3 состояние которые отражают одно и тожее состояние по разному, это может запутать.

Предлагаю оставить одно formState.state
в нем хранить разные типы состояний, например такие `fillig, loading, error, completed`

По одному такому полю можно будет легко понять как именно отрисовывать форму, останется только завести в форму для ошибок - на которые нужно смотреть только в том случае если `formState.state === 'error'`
сейчас похоже выполняет validationResult