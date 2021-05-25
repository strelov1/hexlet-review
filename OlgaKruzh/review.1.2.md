Ольга, добрый день!

Вы хорошо отрефакторили проект, логика значительно упростилась и кода стало ещё меньше, что очень хорошо. Продолжим работу над вашим проектом.

---

https://github.com/OlgaKruzh/frontend-project-lvl1/tree/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943

Директория asciinema осталась в проекте

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/Makefile#L28-L31

Тесты в проекте не реализованы, этот линк может ввести в заблуждение

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/README.md

в README нужно включить инструкцию установки в текстовом формате, чтобы была возможность установить проект скопировав команды в консоль

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/.github/workflows/learn-github-actions.yml

Этот workflow лишний

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/bin/brain-calc.js#L3-L5

Функции глаголы, какой процесс выполняет эта функция?, если перевести его на английский - это будет отличное название функции

Это замечание относится для всех бинарных файлов

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/index.js#L9-L10

В текущем контексте цикл for смотрелся бы лучше

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/index.js#L10

Магические числа, подробнее о них https://ru.hexlet.io/blog/posts/magic-numbers

Следует вынести эту цифру в константу, на уровне модуля, в будущем это позволит тестировать это значение

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/index.js#L12

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/index.js#L15

Не стоит оставлять закомментированный код в проекте, это только усложняет его понимание, а если нужна история с этим уже отлично справляется гит.

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/games/brainCalc.js#L5

Генерацию рандомных чисел стоит выделить в отдельную функцию, тем более она используется не в одной игре, таким образом ее можно будет переиспользовать

Функцию следует поместить в отдельный файл и оттуда ее экспортировать, обычно такой файл называют что-то вроде utils.js

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/games/brainCalc.js#L11-L19

Этот код отличный кандидат для выделения его в отдельную функцию

Оператор switch тут бы смотрелся лаконичнее

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/games/brainEven.js#L8-L16

Также хороший кандидат для выделения
Советую ознакомиться с этой статей, в ней рассматривается этот пример
https://ru.hexlet.io/blog/posts/sovershennyy-kod-proektirovanie-funktsiy

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/games/brainGcd.js#L41-L42

По возможности нужно стараться избегать мутаций переменных, в данном контексте приемлемо:

```
const correctAnswer = calculateDcg(firstOperand, secondOperand).toString();
```

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/games/brainGcd.js#L5-L33

Есть более простой и оптимальный способ найти общий делитель

Попробуйте расписать делители числа 10.

Обратите внимание что если делитель больше половины самого числа, то число не может делиться нацело.

P.S. Подсказку можно найти здесь
https://ru.hexlet.io/courses/programming-basics/lessons/debug/exercise_unit

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/games/brainGcd.js#L3

Стоит вынести в отдельный файл, а также нужно иметь возможность задавать диапазоны минимального и максимального значения

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/games/brainPrime.js#L3-L16

Можно оптимизировать этот алгоритм Math.sqrt(number)

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/games/brainProgression.js#L27-L42

Функция называется createProgression, но она занимается не только созданием прогрессии
следует переписать эту функцию, чтобы у нее была только одна ответственность создания прогрессии

А код занимающийся вскрытием элемента вынести в другую функцию

Также эти обе функции могут быть чистыми, а параметры для генерации принимать в виде аргументов извне, благодаря этому эти функции легко можно будет протестировать

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/games/brainProgression.js#L28-L31

Подобные комментарии, не имеют никакого смысла

Гораздо лучше бы раскрывал смысл, правильно названные имена переменных

Советую прочитать на эту тему главу Самодокументирующийся код из книги С.Макконнелла лучше это никто не объяснит

https://vk.com/doc10903696_270848153?hash=dcba068b9e6fc48203&dl=615f5db8d23a83b8cf

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/games/brainProgression.js#L31-L36

Инициализация первого элемента не очевидный подход, усложняющий код, лучше наполнять с первого элемента в цикле

---

https://github.com/OlgaKruzh/frontend-project-lvl1/blob/ca0ee0c37f8d9fa73b5df1ba71a3b6ed49fe6943/src/games/brainProgression.js#L3-L25

Эти действия лишниее, мы можем узнать правильный ответ, получив случайный индекс в диапозоне прогрессии, потом извлечь его из прогрессии - это будет правильный ответ, далее по этому индексу можно скрыть элемент в прогрессии - это будет наш вопрос (expression)
