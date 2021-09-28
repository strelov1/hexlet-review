https://github.com/1g0rbm/frontend-project-lvl4/blob/241cd961b6a6ba00e07e62398fdb0279b60da299/.gitignore

При такой записи будут игнорироваться как файлы с именем node_modules, так и директории с таким же именем. У нас задача игнорировать директории

https://www.atlassian.com/git/tutorials/saving-changes/gitignore

_________________


https://github.com/1g0rbm/frontend-project-lvl4/blob/241cd961b6a6ba00e07e62398fdb0279b60da299/src/validators.js

Логика вынести все валидаторы в 1 файл ясна, но на практике сталкиваешься с тем что они нужнее там где используются, не приходится прыгать по файлам для чтения кода

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/241cd961b6a6ba00e07e62398fdb0279b60da299/src/components/App.jsx#L17

Это лишний код, этим должен заниматься сам bootstrap, а не делает он из-за поломке в бета версии

https://github.com/1g0rbm/frontend-project-lvl4/blob/241cd961b6a6ba00e07e62398fdb0279b60da299/package.json#L49

Откат на стабильную версию исправит эту проблему

```
"react-bootstrap": "^1.6.1",
```

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/241cd961b6a6ba00e07e62398fdb0279b60da299/src/hooks/useHttp.js

Использования вроде нет, но файл остался

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/241cd961b6a6ba00e07e62398fdb0279b60da299/src/hooks/useSocket.js#L27-L30

Для большей гибкости лучше добавить функцию которая примет в себя ```socket.volatile.emit``` и обернет функционалом потверждения (Acknowledgements) что-то на подобе было с proxy в 3 проекте


_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/241cd961b6a6ba00e07e62398fdb0279b60da299/src/hooks/useSocket.js#L23

Тут reject по таймауту будет производится всегда, даже когда уже отработал resolve выше, чтобы избежать такого поведения нужно отключать таймер перед resolve, похоже есть в примерах
https://socket.io/docs/v3/emitting-events/#acknowledgements

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/241cd961b6a6ba00e07e62398fdb0279b60da299/src/components/Sidebar.jsx#L103

Вся информация для работы с модалкой есть в redux стейте, нет смысла доставать ее в компоненте выше и передавать через пропсы там где исползуется, лучше брать из редакса там где используется

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/241cd961b6a6ba00e07e62398fdb0279b60da299/src/components/modal/AddChannel.jsx#L33

Работа с formik через hook useFormik предпочтительней https://formik.org/docs/api/useFormik

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/241cd961b6a6ba00e07e62398fdb0279b60da299/src/components/modal/AddChannel.jsx#L77

formik.isDirty вместо values.name 

formik.isValid вместо !!errors?.name

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/241cd961b6a6ba00e07e62398fdb0279b60da299/src/components/modal/AddChannel.jsx#L21


В компоненте уровнем выше мы можем подготовить сразу такую функцию, чтобы не делать это в каждой модалке

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/241cd961b6a6ba00e07e62398fdb0279b60da299/src/components/Chat.jsx#L14-L22

Это вызывает такой warning, их тоже нужно смотреть и устранять

https://github.com/1g0rbm/frontend-project-lvl4/runs/3707794845#step:3:331

_________________

https://github.com/1g0rbm/frontend-project-lvl4/blob/241cd961b6a6ba00e07e62398fdb0279b60da299/src/components/Chat.jsx#L21

Здесь может возникнуть проблема установки состояние даже после того как компонент был отремонтирован (в случае задежки ответа api)

Чтобы избежать такого нужно добавить флаг 

https://academind.com/tutorials/useeffect-abort-http-requests#preventing-memory-leaks