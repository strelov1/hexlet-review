Добрый день. Игорь! Отличная работа!

Сейчас наступает не менее важная часть разработки - рефакторинг кода. Далее я отправлю список замечаний.
Ваша задача внимательно изучить их и внести исправления в свой код

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/7d90dd0d5655960b738de11445c1a831a81f3004/README.md

На странице должны отображаться сами аскинемы, а не ссылки на них. Так проект будет выглядеть более привлекательно для потенциальных работодателей, которые будут просматривать ваш репозиторий. Просмотрите как можно встроить на страницу аскинему https://asciinema.org/docs/embedding

---

Также в README можно включить инструкцию установки в текстовом формате, чтобы была возможность установить скопировав команды

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/7d90dd0d5655960b738de11445c1a831a81f3004/bin/brain-calc.js#L4-L6

Данная часть проекта должна отвечать только за его запуск игры, сконфигурировать игру можно в файле самой игры, это замечание касается всех игр

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/7d90dd0d5655960b738de11445c1a831a81f3004/src/games/brain-calc.js#L27-L29

Эти операции должны быть часть игрового движка, сама игра должна только подготавливать для движка данные, благодаря такому подходу изменения взаимодействия с пользователем можно будет делать в одном файле, причем выделение этих операций в функции не решает проблему, рассмотрите к примеру случай, что у нас появилась необходимость переписать эти операции на асинхронный подход, сколько кода придется переписать?

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/7d90dd0d5655960b738de11445c1a831a81f3004/src/games/brain-calc.js#L24

Это не операция а индекс операции, также если у нас изменится состав операций, там опять придется высчитывать индексы для того чтобы генерация раномного числа не вышла за пределы

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/7d90dd0d5655960b738de11445c1a831a81f3004/src/games/brain-calc.js#L8-L17

Если увидеть эту функцию без контекста, можно ли сходу понять что она делает и какие аргументы ожидает?

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/7d90dd0d5655960b738de11445c1a831a81f3004/src/games/brain-calc.js#L14-L15

Дефолтное поведение в этого свитча может повести себя очень странно если передать неверную операции, подробнее можно почитать здесь https://ru.hexlet.io/blog/posts/sovershennyy-kod-defolty-v-svitchah

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/7d90dd0d5655960b738de11445c1a831a81f3004/src/mathematic.js#L32-L42

Интересное применение навыков с итеративной рекурсией, вижу что вы отлично поняли как она работает, но в данном конексте это только усложняет процесс понимания :-)

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/7d90dd0d5655960b738de11445c1a831a81f3004/src/games/brain-prime.js#L4-L9

Это тоже интересное решение, но опять же попахивает оверинжинирингом, решается сложным способом что можно сделать проще, подробнее о проектировании функции можно посмотреть https://ru.hexlet.io/blog/posts/sovershennyy-kod-proektirovanie-funktsiy

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/7d90dd0d5655960b738de11445c1a831a81f3004/src/mathematic.js

Эти функции, пожалуй кроме generateRandomNumber, не являются универсальными для проекта, и не будут использоваться в разных играх, а пренадлежат именно доменной области отдельных игр, логичным было бы их размещать в файлах с самими играми для, которых эти функции были бы нужны

---

https://github.com/1g0rbm/frontend-project-lvl1/blob/7d90dd0d5655960b738de11445c1a831a81f3004/src/dialog.js

Есть ли смысл выносить эти операции в отдельную функцию, делает ли это код проще для чтения, функции должны скрывать за собой какую-либо абстракцию, что скрывают данные функции, кроме say, ну и логично уже было бы добавить противоположную ask `const ask = (msg) => readlineSync.question(msg)`
