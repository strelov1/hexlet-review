
---

https://github.com/Finnko/frontend-project-lvl1/blob/bfb61b71aa97ddc056b0f26eb3a10b54199406e8/README.md

Записи asciinema пропали, скорее всего это означает что они загружались анонимно, нужно было зарегистрироваться и связать консольное приложение со своей учтой записью

https://asciinema.org/docs/getting-started

```asciinema auth```

---

https://github.com/Finnko/frontend-project-lvl1/blob/bfb61b71aa97ddc056b0f26eb3a10b54199406e8/src/utils.js#L1

Не стоило задавать в этой функции значения по умолчанию, если мы заходим их поменять, то может сломаться какая-то игра, лучше задавать эти значения при вызове каждый раз, но если очень хочется то можно перднастроить эту функцию по месту

```
const getRandomRangeHundreds = () => getRandom(0, 100);
getRandomRangeHundreds();
```