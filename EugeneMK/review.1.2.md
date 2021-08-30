Евгений, день добрый!

Вы хорошо отрефакторили проект, логика значительно упростилась и кода стало ещё меньше, что очень хорошо. Продолжим работу над вашим проектом.

https://github.com/EugeneMK/frontend-project-lvl1/blob/ec429f058ed26db2a35c344bd3713639ffcf6af0/Makefile#L10

make в Makefile уже не нужно писать


---

https://github.com/EugeneMK/frontend-project-lvl1/blob/ec429f058ed26db2a35c344bd3713639ffcf6af0/README.md

Ссылка на codeclimate ведет на тестовый репозиторий codeclimate

---

https://github.com/EugeneMK/frontend-project-lvl1/blob/ec429f058ed26db2a35c344bd3713639ffcf6af0/src/cli.js#L5-L9

Проблема не ушла, у нас также есть функция, которая делает слишком много, получает пользователя, приветствует, возвращает его имя

---

https://github.com/EugeneMK/frontend-project-lvl1/blob/ec429f058ed26db2a35c344bd3713639ffcf6af0/bin/brain-games.js#L4-L5

Достаточно вызова одной функции, Проблема с функцией greeting из предыдущей версии (https://github.com/EugeneMK/frontend-project-lvl1/blob/4eadf0c27cdc7b33c645a4b2809ae8e424cc18c3/src/cli.js#L3-L8) в том что она возвращает имя пользователя, и используется в других участках кода

---

https://github.com/EugeneMK/frontend-project-lvl1/blob/ec429f058ed26db2a35c344bd3713639ffcf6af0/src/index.js#L7

Повторюсь...

На 5 шаге указано 

```
Файл cli.js не предназначен для описания логики игр.
Файлы, которые мы добавили ранее (src/cli.js, bin/brain-games.js), оставьте как есть и не смешивайте с остальным кодом.
```

---

https://github.com/EugeneMK/frontend-project-lvl1/blob/ec429f058ed26db2a35c344bd3713639ffcf6af0/src/index.js#L11

В нашей науке принято начинать счет с 0, кроме исключительных ситуаций - наша ситуация не исключительна

---

https://github.com/EugeneMK/frontend-project-lvl1/blob/ec429f058ed26db2a35c344bd3713639ffcf6af0/src/games/calc.js#L6-L10

За это лайк, крутой подход, но есть 2 момента

https://github.com/EugeneMK/frontend-project-lvl1/blob/ec429f058ed26db2a35c344bd3713639ffcf6af0/src/games/calc.js#L16

Само вычисление все же стоит выделить в отдельную функцию, чтобы оно не было похоже на магию

Также нужно не забыть обработать возможные ошибки, если придет не тот оператор

---

https://github.com/EugeneMK/frontend-project-lvl1/blob/ec429f058ed26db2a35c344bd3713639ffcf6af0/src/games/gcd.js#L14-L16

Непонятно для чего нужен divider

---

https://github.com/EugeneMK/frontend-project-lvl1/blob/ec429f058ed26db2a35c344bd3713639ffcf6af0/src/games/progression.js#L7-L15

Функцию генерацию прогрессии и форматирования вопроса из нее (скрытие элемента) лучше разделить на 2 разные функции