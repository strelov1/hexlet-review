https://github.com/Finnko/frontend-project-lvl4/blob/7d4cbae862adb593439886d1e8011fc614c703b8/src/components/Channels/Channels.jsx#L53

Вот в таких моментах лучше подготовить функцию заранее, такие функции просто виднее в коде

```
const handleAddChannel = () => dispatch(showModal({ type: ModalType.NEW_CHANNEL }))
```