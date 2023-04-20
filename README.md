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
	- var destination = document.querySelector("#some"); // outside render // before component class.
## Компоненты React
```jsx
class ComponentName extends React.Component {
	render(){
		var xStyle = {backgroundColor: this.props.bgcolor}; /* css styles */

		return (
			<div style={xStyle}>
				<button type={this.props.behavior}>
					{this.props.children}
				</button>
			</div>
		)
	}
}
ReactDOM.render(
	<div>
		<ComponentName bgcolor="#ff605f" behavior="submit">Send Data</ComponentName>
	</div>, destination);
```
#стилизация
- className!! instead of class(js)  
[Руководство по трём способам стилизации в React](https://medium.com/@stasonmars/%D1%80%D1%83%D0%BA%D0%BE%D0%B2%D0%BE%D0%B4%D1%81%D1%82%D0%B2%D0%BE-%D0%BF%D0%BE-%D1%82%D1%80%D1%91%D0%BC-%D1%81%D0%BF%D0%BE%D1%81%D0%BE%D0%B1%D0%B0%D0%BC-%D1%81%D1%82%D0%B8%D0%BB%D0%B8%D0%B7%D0%B0%D1%86%D0%B8%D0%B8-%D0%B2-react-2ca5c0c7464b)
# counter
ReactAPI

важно !!! (создаем объект state перед созданием компонента)
```jsx
class ComponentName extends React.Component {
constructor(props) { // ???
				super(props); // ???

				this.state = { strikes: 0 };
				this.timerTick = this.timerTick.bind(this); // bind timer
}
timerTick() { // timer
				this.setState({
					strikes: this.state.strikes + 100 // update value
				});
			}

			componentDidMount() { // after component render
				setInterval(this.timerTick, 1000); 
			}
render(){
	var count = this.state.strikes.toLocaleString();
	return( {count} )} // render
```