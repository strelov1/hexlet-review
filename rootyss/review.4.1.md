
Привет! И сразу к делу


https://github.com/rootyss/frontend-project-lvl4/blob/7178dd720a4e5fc84f9e7518be5d545fd8ea6846/README.md

README.md Пуст - сюда точно заглянет потенциальный работодатель, и он бы смотрелся круче с инструкцией установки

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/7178dd720a4e5fc84f9e7518be5d545fd8ea6846/package.json#L4

Тоже зияющая пустота

_________________


На 6 шаге есть указания
https://ru.hexlet.io/projects/12/members/16921?step=6

```
Фокус устанавливается в соответствующее поле ввода
```

Фокус в эталонном проекте установлен автоматически на поле ввода текста, при переключения чата также не срабатывает фокусировка

При добавлении нового канала по нажатию Enter форма не сабмитится а модалка закрывается, ожидаемое поведение отправка данных, как при редактировании

Если имя канала длинное, оно выезжает на верстку чата

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/7178dd720a4e5fc84f9e7518be5d545fd8ea6846/src/utils.js

Функции для работы с аутентификацией и пользователям удобнее поместить в контекст а использование контекста удобнее организовать через хук

_________________

https://github.com/rootyss/frontend-project-lvl4/tree/7178dd720a4e5fc84f9e7518be5d545fd8ea6846/src/context

Файлы не содержащие JSX принято называть js

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/7178dd720a4e5fc84f9e7518be5d545fd8ea6846/src/init.jsx#L24-L62

Компоненты нужно объявлять на уровне модуля а не внутри функции, это позволит избежать использование переменных из компонента выше - тем самым они становятся глоабьными и в этом легко запутаться

В данном случае объявление отдельного компонента выглядит излишне

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/7178dd720a4e5fc84f9e7518be5d545fd8ea6846/src/init.jsx#L38

Для большей гибкости лучше добавить функцию которая примет в себя ```socket.volatile.emit``` и обернет функционалом потверждения (Acknowledgements) что-то на подобе было с proxy в 3 проекте

Также не хватает блокировки как здесь https://socket.io/docs/v3/emitting-events/#acknowledgements
```  
let called = false;
if (called) return;
```
В случаях гонки может возникнуть ситуация когда успеет отработать и reject и resove что может привести к неожиданному поведению

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/7178dd720a4e5fc84f9e7518be5d545fd8ea6846/src/components/Channel.jsx#L31-L60

Такие большие тернарные операторы читаются плохо, лучше вынести в функцию в которой сделать явное ветвление по if

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/7178dd720a4e5fc84f9e7518be5d545fd8ea6846/src/components/LoginPage.jsx#L46

Пути это точка изменений, лучше выделить отдельные функции для формирования таких путей

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/7178dd720a4e5fc84f9e7518be5d545fd8ea6846/src/components/Chat.jsx#L85-L111

Форму для ввода сообщения лучше выделить в отдельный компонент, это упростит чтение и дальнейшее поддержание

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/7178dd720a4e5fc84f9e7518be5d545fd8ea6846/src/components/Chat.jsx#L123-L125

Здесь может возникнуть проблема установки состояние даже после того как компонент был отремонтирован (в случае задежки ответа api)

Чтобы избежать такого нужно добавить флаг 

https://academind.com/tutorials/useeffect-abort-http-requests#preventing-memory-leaks

_________________

https://github.com/rootyss/frontend-project-lvl4/blob/7178dd720a4e5fc84f9e7518be5d545fd8ea6846/src/components/Chat.jsx#L63-L74

Кнопку создания нового канала тоже имеет смысл поместить в компонент управления каналами

_________________

https://github.com/rootyss/frontend-project-lvl4/tree/7178dd720a4e5fc84f9e7518be5d545fd8ea6846/src/components

Компоненты начинающиеся на Modal так и просят отдельной директории
_________________


https://github.com/rootyss/frontend-project-lvl4/blob/7178dd720a4e5fc84f9e7518be5d545fd8ea6846/src/components/ModalWindow.jsx#L38-L41

Это все лучше достать в самой модалке, если он там вообще будет нужно