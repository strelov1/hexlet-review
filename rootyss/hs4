https://github.com/rootyss/frontend-project-lvl1/blob/3b1e10e831229daefcdbda4d3571dcfbb4bbc91b/package.json#L4

Это описание попадает в npm репозиторий, разработчикам наткнувшийся на новый пакет было бы приятно если бы из этого описания сразу можно было понять о чем проект
_________________

https://github.com/rootyss/frontend-project-lvl1/blob/3b1e10e831229daefcdbda4d3571dcfbb4bbc91b/src/games/calc.js#L7

Имя функции должна быть глаголом, не стоит использовать сокращения: `calc, Exp` сами по себе не такие плохие сокращения,
но в нашем случае они нам мешают тем, что ломают семантику описания функции,
если задать вопрос что делает calcExp - без контекста, мы не разберемся что она делает. a,b - это тоже сокращения, 
которые совершенно не говорят нам о том что из себя они представляют
_________________

`${param}` - такой подход называется интерполяция строки он удобен в таких случаях
 https://github.com/rootyss/frontend-project-lvl1/blob/3b1e10e831229daefcdbda4d3571dcfbb4bbc91b/src/games/calc.js#L26
_________________

но в таких случаях
https://github.com/rootyss/frontend-project-lvl1/blob/3b1e10e831229daefcdbda4d3571dcfbb4bbc91b/src/games/calc.js#L25

он может сбить с толку, есть более явные способы преобразования в строку например `String(value)`
_________________

https://github.com/rootyss/frontend-project-lvl1/blob/3b1e10e831229daefcdbda4d3571dcfbb4bbc91b/src/games/calc.js#L24

переменная хранит просто рандомное число, а не оператор, было бы логичнее хранить именно рандомные оператор в этой переменной

`operators[getRandomNum(0, operators.length - 1)]`

_________________

https://github.com/rootyss/frontend-project-lvl1/blob/3b1e10e831229daefcdbda4d3571dcfbb4bbc91b/src/games/prime.js#L8-L11

Здесь снова экономия на переносах строк и блочных скобках
_________________

https://github.com/rootyss/frontend-project-lvl1/blob/3b1e10e831229daefcdbda4d3571dcfbb4bbc91b/src/games/progression.js#L28

https://github.com/rootyss/frontend-project-lvl1/blob/3b1e10e831229daefcdbda4d3571dcfbb4bbc91b/src/games/progression.js#L30

Мутировать переменную progression в данном случае совершенно не имеет смысла
_________________

genQuestionGame - возвращает уже Question а не прогрессию, было бы правильным сохранить это в собственную переменную (не забываем про именования), и не пришлось бы мутировать переменную progression

https://github.com/rootyss/frontend-project-lvl1/blob/3b1e10e831229daefcdbda4d3571dcfbb4bbc91b/src/games/progression.js#L17-L21

Мы задаем пользователю вопрос , но в нашем случае он сформирован не полностью и его нужно обрабатывать ниже, в местах которые не должны знать об этих моментах преобразоывания

`return progWithHiddenElem.join(' ');`
_________________

https://github.com/rootyss/frontend-project-lvl1/blob/3b1e10e831229daefcdbda4d3571dcfbb4bbc91b/src/index.js#L30
лишняя открывающая кавычка в начале строки