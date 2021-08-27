Поздравляю с успешным завершением проекта!

---

И небольшое домашнее задание:

https://github.com/eyt5297/frontend-project-lvl2/blob/e094b5f6e8e1ca202609299620750966490dbca5/src/index.js#L14

Можно ведь просто added.

---

/src/parsers.js – имя модуля всё же стоит изменить. Это не парсеры, это именно парсер. На выходе мы ведь получаем уже обработанные данные. Можно глянуть, как форматеры сделаны.

---

https://github.com/eyt5297/frontend-project-lvl2/blob/e094b5f6e8e1ca202609299620750966490dbca5/src/index.js#L7-L35

Эта функция достойна отдельного модуля.

---

https://github.com/eyt5297/frontend-project-lvl2/blob/e094b5f6e8e1ca202609299620750966490dbca5/src/index.js#L40-L41

Побочные эффекты лучше вынести из основной функции.