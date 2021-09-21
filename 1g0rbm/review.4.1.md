
Привет! Хорошая работа! Приступим к рефакторингу.

На 6 шаге есть указания
https://ru.hexlet.io/projects/12/members/16797?step=6

```
Фокус устанавливается в соответствующее поле ввода
```

Фокус в эталонном проекте установлен автоматически на поле ввода текста, при переключения чата также не срабатывает фокусировка

При вводе неверного логина/пароля нет фокусировки на форме как в эталоне
_________________


https://github.com/1g0rbm/frontend-project-lvl4/blob/e11ccbbbc9997335dc67f09c3595ca331e9711a0/src/locales/ru.js#L10

При редактировании имени канала - кнопка открывающая окно редактирования

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/e11ccbbbc9997335dc67f09c3595ca331e9711a0/src/validators.js#L33

Имя канала не может быть с большой буквы, в эталонном проекте это не так

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/e11ccbbbc9997335dc67f09c3595ca331e9711a0/src/hooks/useHttp.js

Данная абстракция больше усложняет код чем помогает

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/e11ccbbbc9997335dc67f09c3595ca331e9711a0/src/components/Chat.jsx#L10

Удобнее было бы обращение к этому контексту изолировать в хуки, в нем и реализовать методы логина логаута через которые будет обновляться информация в контексте

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/e11ccbbbc9997335dc67f09c3595ca331e9711a0/src/components/Chat.jsx#L25

На request хук не должен реагировать, там и не должно что-то меняться, а вот на изменения роута в history должен

_________________


https://github.com/1g0rbm/frontend-project-lvl4/blob/e11ccbbbc9997335dc67f09c3595ca331e9711a0/src/components/LoginForm.jsx#L63

Это тоже очень сомнительная практика, хранит в хуке ошибки и очищать, лучше сделать явный флаг наличия ошибки в catch запроса

_________________


https://github.com/1g0rbm/frontend-project-lvl4/blob/e11ccbbbc9997335dc67f09c3595ca331e9711a0/src/components/LoginForm.jsx#L62

Что еще за `bag`?

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/e11ccbbbc9997335dc67f09c3595ca331e9711a0/src/index.jsx#L14

Уже можно и await


_________________


https://github.com/1g0rbm/frontend-project-lvl4/blob/e11ccbbbc9997335dc67f09c3595ca331e9711a0/src/hooks/useSocket.js#L8

Для гарантий доставки socket.volatile.emit
И лучше изолировать методы newMessage, newChannel и т.д в отдельные функции а не делать прописывать это по месту, можно поместить эти функции в контекст чтобы проще было использовать по месту

https://github.com/1g0rbm/frontend-project-lvl4/blob/e11ccbbbc9997335dc67f09c3595ca331e9711a0/src/components/modal/AddChannel.jsx#L39-L51

Также нужно реализовать принудительные reject если не дождались ответа от сервера через таймаут