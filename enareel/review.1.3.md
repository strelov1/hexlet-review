Ранее уже писал о директории games

https://github.com/enareel/frontend-project-lvl1/tree/84dc3eae83e26012d16632ec45701cfb9fa62c62/games

Директория src должна содержать исходный код программы,
Игры также являются исходным кодом

---


https://github.com/enareel/frontend-project-lvl1/blob/84dc3eae83e26012d16632ec45701cfb9fa62c62/games/brain-progression.js#L33

Что значит diff здесь совершенно не понятно, только изучив код понял что это шаг прогрессии, его следует так и называть step

---

https://github.com/enareel/frontend-project-lvl1/blob/84dc3eae83e26012d16632ec45701cfb9fa62c62/games/brain-progression.js#L44-L45

Формирование выражения тоже стоит вынести в отдельную функцию, чтобы не пришлось мутировать переменную progression