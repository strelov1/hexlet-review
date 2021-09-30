https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/Channels.jsx#L20

Имя компонента Channels некорректно отражает суть компонента, здесь скорее ChannelBox

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/Channels.jsx#L9-L18

Если объявить эти функции внутри компонента Channels, то можно сразу использовать dispatch и не придется передавать его в подготавливающий вызов

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/Channels.jsx#L35

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/Channel.jsx#L15-L89

Здесь разделение на 2 компонента выглядит неоправданным

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/Channel.jsx#L45

Скрыть вышедший из зоны видимости контент правильнее будет с помощью css

```
overflow: hidden;
text-overflow: ellipsis;
```

_________________


https://github.com/rootyss/frontend-project-lvl4/blob/main/src/store/slice.js#L6-L21

Эти функции уже есть

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/App.jsx#L19-L27

Нужно их объявить в одном месте

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/store/slice.js

Лучше разбить этот файл на несколько для каждого слайса, для thunks тоже стоит выделить отдельный файл

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/App.jsx#L56

PrivateRoute имя лучше бы раскрыло смысл

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/Signup.jsx#L121-L126

Можно поместить ниже в Form.Control.Feedback

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/Signup.jsx#L131-L137

Нет блокировки кнопки на isSubmiting


_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/Signup.jsx#L46

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/LoginPage.jsx#L50

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/LoginPage.jsx#L125

Путь стоит сохранить в маршрутах

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/Chat.jsx#L45-L48

Такая защита не сработает, проверка должна быть до загрузки данных в стейт

Если на момент получения данных компонент отмонтируется, а данные будут еще загружаться, после их загрузки уже не нужно будет помещать их в стейт

_________________


https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/FormMessage.jsx#L67-L69

Для иконок удобнее было бы использовать этот пакет

https://www.npmjs.com/package/react-bootstrap-icons

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/main/src/components/NavBar.jsx#L16

Обычно использует имя предиката isGuest

_________________

https://github.com/rootyss/frontend-project-lvl4/tree/main/src/components/Modals

Директории принято называть с маленькой буквы

Внутри директории modals из контекста ясно что это модальные окна, нет необходимости это прописывать в каждом имени компонента

Для ModalWindow.jsx в этом месте подошло бы имя index.jsx
