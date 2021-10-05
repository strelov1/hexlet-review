

https://github.com/1g0rbm/frontend-project-lvl4/blob/main/src/slices/modalDataSlice.js#L14

Для каждой модалки отдельный экшен. Согласно паттерну экшен 1 и принимает тип открываемой модалки

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/main/src/components/Chat.jsx#L24

Относится к авторизации, можно вынести как функцию получения заголовков в authApi

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/main/src/components/Messages.jsx#L42

Селекторы объявляются вне реакта

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/main/src/components/MessageForm.jsx#L25

Формик сам умеет обрабатывать промис возвращаемый из сабмита, достаточно ретурн поставить