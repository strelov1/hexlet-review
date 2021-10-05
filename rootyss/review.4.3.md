https://github.com/rootyss/frontend-project-lvl4/blob/main/src/init.jsx#L7

Не должно быть глобальных состояний

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/store/index.js#L7

Код выполняется во время импорта

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/utils.js#L1

Вся авторизация не верно сделана. Используется как глобальное состояние

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/utils.js#L19

Сторадж читается 1 раз за все время жизни приложения

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/App.jsx#L22

То есть если чел залогинился - он гость?

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/store/createAsyncThunk.js#L16

rejectWithValue

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/Signup.jsx#L44

Это все к авторизации, в коде не должно быть обращения к стораджу

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/Messages.jsx#L11

Селекторы объявляются вне реакта

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/Chat.jsx#L45-L51

Это нужно убрать, оставить только `dispatch(fetchInfo());`

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/Chat.jsx#L18

currentChannel?.name