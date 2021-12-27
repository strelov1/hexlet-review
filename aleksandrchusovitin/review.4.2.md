https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/init.jsx#L16-L21

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/init.jsx#L33

Может быть спорный момент, но в некоторых случаях распаковка просто не нужна,
вот так будет читаться даже лучше

```
store.dispatch(actions.addMessage(payload));
```

---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/locales/i18next/i18next.js#L5-L19

Знаю что такое рекомендуют в доке, но такой вариант не будет корректно работать при определнных обстоятельствах, к примеру если у нас в локале будет много переводов может случиться так что приложение загризится раньше загругки переводов, это по сути состояние гонки и единственный способ сделать это праильно подключать асинхронно при инициализации как мы это делали в 3 проекте


---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/index.js#L6-L7

Инициализацию сокета и работу с домом также стоит вынести в функции которая тут же и будет вызываться, такой способ избавит от возможных коллизий с однинаковыми именами переменных


---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/init.jsx#L45-L52

Чтобы не было ошибок rollbar в тестах, просто не включаем его там

```
enabled: process.env.NODE_ENV === 'production',
```

---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/pages/Login.jsx#L54

Можно выбросить toast с сетевой ошибкой на этот случай если не 401

Аналогично здесь если не 409

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/pages/SignUp.jsx#L62

---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/pages/SignUp.jsx#L62

Тоже распаковка выглядит избыточной

```
auth.login(res.data)
```

---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/pages/MainPage.jsx#L25-L36

Здесь может возникнуть проблема установки состояние даже после того как компонент был отмонтирован (в случае задежки ответа api)

Подробнее о проблеме
https://github.com/facebook/react/issues/14369

Чтобы избежать такого нужно добавить флаг 
Как сделать
https://academind.com/tutorials/useeffect-abort-http-requests#preventing-memory-leaks


---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/pages/MainPage.jsx#L36

Незабываем устанавливать зависимости, по сути все объявленные выше функции являются зависимостями для этого эффекта


---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/components/Channels.jsx#L18

Правильнее будет извлекать
```
const { channels, currentChannelId } = useSelector((state) => state.channelsReducers);
```

---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/components/Channels.jsx#L94

Отрисовку отдельного канала также хорошо бы вынести в отдельный компонент

```
renderSplitButton(name, id, isCurrentChannel)
renderGeneralButton(id, name, isCurrentChannel)}
```

Не консистентный порядок аргументов смущает

---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/components/SubmitMessage.jsx#L40-L41

Такое нужно подключать в init.jsx, у компонента много жизненных циклов, это значит что код который определен в его теле может запускаться огромное количетство раз, но подключение библиотеки достаточно сделать 1 раз

---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/providers/SocketProvider.jsx#L17-L19

Универсально все ошибки не стоит обрабатывать, лучше это делать по месту вызова, там больше контроля над состояние ошибки

Здесь просто reject()

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/components/SubmitMessage.jsx#L34

А вот здесь отлов и обработка, добавление toast, rollar и т.д

---


https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/components/SubmitMessage.jsx#L73

Кнопка отправить должна быть заблокирована, когда у нас ошибка в formik


---



https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/components/modals/index.jsx#L16


Какое-то обратное извлечение из стейта, у нас для этого служит функция селектора


```
const isOpened = useSelector((state) => state.modalReducers.isOpened);
```


channelsReducers = это получить лучше там где он нужен, базовая модалка ничего не должна знать о каналах


Но вот о чем она должна знать так это о том как модалку закрывать


https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/components/modals/AddChannel.jsx#L63


Этот код вынести выше в уровень modals/index.jsx



https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/components/modals/index.jsx#L20-L22


```
<Modal show={!isOpened}
```


---


https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/26b63f5b8ebfbbeb2f07ef39aa39a427a8b30370/src/components/Chat.jsx#L24-L30


Отличный кандидат на выделение отдельного компонента Message, а вот итерацию map лучше оставить на месте


```
<div ref={messagesBoxRef} id="messages-box" className="chat-messages overflow-auto px-5">
    {messagesForCurrentChannel.map((props) => <Message {...props}>)}
</div>
```
