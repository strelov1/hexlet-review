https://github.com/rootyss/frontend-project-lvl2/blob/522aa6b2311ee6d845c81d6183243cd83513fd01/src/getObjDifference.js#L29

Вторая проверка здесь лишняя

_________________

https://github.com/rootyss/frontend-project-lvl2/blob/522aa6b2311ee6d845c81d6183243cd83513fd01/src/index.js#L10-L11

Так все же будет лучше:

```
const parse = (ext, content) => getParser(ext)(content);
parse(getFileExt(filepath2, contentFile2));
```
