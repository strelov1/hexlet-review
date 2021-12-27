Привет и сразу к делу!

https://github.com/aleksandrchusovitin/frontend-project-lvl4/tree/1f669562581f01afb77093a4ec503cc0bbec6790/src/components

Касательно раскладывание приложение по директориям более приятный подход
App.js и pages вынести на уровень корня ```src`` 
components - все же про какие-то независимые от места расположения части приложения

Более продвинутая архитектура, ее реализовать не прошу, но хотя бы ознакомиться стоит
https://medium.com/@nik.152002/%D0%B0%D1%82%D0%BE%D0%BC%D0%BD%D1%8B%D0%B9-%D0%BF%D0%BE%D0%B4%D1%85%D0%BE%D0%B4-%D0%B2-react-59db5ac1ee7e

---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/1f669562581f01afb77093a4ec503cc0bbec6790/src/components/app/App.jsx#L70-L93

Эта часть кода является инициализацией приложения и её самое место в файле init.jsx

---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/6a8f1b09bb358b2907c2f7511a1b2051cb810a4c/src/store/index.js#L6-L11

Эту часть тоже нужно перенести в init.js, так у тебя получается стор становится глобальным, а в этом месте нужно собрать все редьюсеры combineReducers и экшены для удобного использования


---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/1f669562581f01afb77093a4ec503cc0bbec6790/src/components/pages/MainPage.jsx#L217-L224

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/1f669562581f01afb77093a4ec503cc0bbec6790/src/components/pages/MainPage.jsx#L301

Этот код должен лежать здесь

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/1f669562581f01afb77093a4ec503cc0bbec6790/src/components/modals/index.js

А подключаться здесь на уровне под ErrorBoundary, чтобы вызвать модалки можно было бы с любого места, то же касается подключения ToastContainer


---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/1f669562581f01afb77093a4ec503cc0bbec6790/src/components/modals/RemoveChannel.jsx#L26-L36

Всю работу с сокетами вынести в отдельное апи - объект предоставляющих все функции, само апи распространяй по компонентам через контекст, аналогично функциям авторизации

---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/1f669562581f01afb77093a4ec503cc0bbec6790/src/components/modals/RemoveChannel.jsx#L14-L21

Всю логику работы со стейтом в модалках вынести на уровень выше в родительский компонент модалки, а в сами модальные окна только передавай нужные функции обработчики

---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/1f669562581f01afb77093a4ec503cc0bbec6790/src/components/pages/MainPage.jsx

Этот компонент нужно разбить на функциональные

Компонент отрисовывающий чаты с возможностью переключаться по ним

Компонент отображающий чат

Компонент отвечающий за форму отправки сообщения


---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/1f669562581f01afb77093a4ec503cc0bbec6790/src/components/pages/NavBar.jsx

NavBar - это никак не page


---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/1f669562581f01afb77093a4ec503cc0bbec6790/src/store/slices/modalSlice.js#L5

Из состояния modal = null нельзя понять за что оно отвечает, стоит внести состояние isOpened, и тип модалки

И соответвующие редюсеры openModal, closeModal? через которые можно открывать нужные нам модалки - modalSetting выглядит странновато

---

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/1f669562581f01afb77093a4ec503cc0bbec6790/src/store/slices/channelsSlice.js#L14-L26

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/1f669562581f01afb77093a4ec503cc0bbec6790/src/store/slices/messagesSlice.js#L14-L23


Зачем нам здесь загрузка ошибок не понятно, даже не нашел использование этого состояния в коде messagesLoadingStatus

Если бы у нас загрузка была не из вне редакса а с помощью saga или thunk это было бы понятно, но в таком случае бы тоже не пришлось присать руками таких редьсеров

Сделай по 1 му редьюсеру с одниковым именем для загрузки данных 
и вызови одноименный редьсер здесь 

https://github.com/aleksandrchusovitin/frontend-project-lvl4/blob/1f669562581f01afb77093a4ec503cc0bbec6790/src/components/pages/MainPage.jsx#L68-L70