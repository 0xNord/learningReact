# learningReact - Заметки

## Подключаем React
```html
<script src="https://unpkg.com/react@16/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@16/umd/react-dom.development.js"></script>
```
- Добавляем ссылку на компилятор для js - Babel(babeljs.io).  
- позволяет превращать код JSX в JavaScript.
```html
<script src="https://unpkg.com/babel-standalone@6.15.0/babel.min.js"></script>
```
## методы React
- ReactDOM.render(JSX,destination);
	- destination = document.querySelector("#some");
