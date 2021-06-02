Итак, продолжим...

---

https://github.com/askorutin26/frontend-project-lvl1/tree/1150f8b0905539c5025315dae04a113d7152066e#how-to-install

Для того чтобы код или команды в консоли в readme выглядел лучше его нужно обрамлять специальными кавычками
https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#quoting-code



---

https://github.com/askorutin26/frontend-project-lvl1/tree/1150f8b0905539c5025315dae04a113d7152066e/src/games

Имя Engine в файлах лишнее, эти файлы не являются движками


---

https://github.com/askorutin26/frontend-project-lvl1/blob/1150f8b0905539c5025315dae04a113d7152066e/src/games/brain-Calc-Engine.js#L2

Эту функцию не стоило выделять в отдельный файл, она имеет непосредственное отношения к этой игре, и нигде более не используется

---


https://github.com/askorutin26/frontend-project-lvl1/blob/1150f8b0905539c5025315dae04a113d7152066e/src/games/brain-Calc-Engine.js#L13

`(expressionElements[1]` 1 здесь магическое число, как понять что оно значит не прочитав весь код?
подробнее о них https://ru.hexlet.io/blog/posts/magic-numbers

---

https://github.com/askorutin26/frontend-project-lvl1/blob/1150f8b0905539c5025315dae04a113d7152066e/src/games/brain-Calc-Engine.js#L13-L15

Предыдущий вариант с маппингом выражений был лучше, необходимо было только вынести эти действия в отдельную функцию

https://github.com/askorutin26/frontend-project-lvl1/blob/c12ecb5fb67b1e71563ff01ebf7554e1c0f1702e/src/games/brain-Calc-Engine.js#L24-L29

---


https://github.com/askorutin26/frontend-project-lvl1/blob/1150f8b0905539c5025315dae04a113d7152066e/src/games/brain-Even-Engine.js#L7-L12

https://github.com/askorutin26/frontend-project-lvl1/blob/1150f8b0905539c5025315dae04a113d7152066e/src/games/brain-Prime-Engine.js#L8-L14

Подстройка поведения функции под интерфейс, советую еще раз внимательнее ознакомиться со статьей https://ru.hexlet.io/blog/posts/sovershennyy-kod-proektirovanie-funktsiy

---

https://github.com/askorutin26/frontend-project-lvl1/blob/1150f8b0905539c5025315dae04a113d7152066e/src/games/brain-Progression-Engine.js#L4-L41

Здесь очень четко прослеживается проблема которая есть во всех играх, мы посылаем данные из движка обратно в игру, из-за чего приходится делать огромное количетсво обратных вычислений и преобразований, когда мы могли сразу подготовить все данные для движка, как верный ответ так и сам вопрос в игре, а движку просто делегировать сверку пользовательского ответа с исходным 


---

https://github.com/askorutin26/frontend-project-lvl1/blob/1150f8b0905539c5025315dae04a113d7152066e/src/index.js#L10

И снова магическое число, нужно выделить это значение в отдельную константу, из чего будет ясно что эта цифра значит, а также бонусом появится возможность протестировать это значение в будующем

---

https://github.com/askorutin26/frontend-project-lvl1/blob/1150f8b0905539c5025315dae04a113d7152066e/src/games/brain-Progression-Engine.js#L12-L17

Почему `y` ? Стоит выделить код генерации прогрессии в отдельную функцию

