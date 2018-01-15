## Instructions
1. Set up npm, babel-react and babel env
2. Use npm-start to run server
## Coding syntax
### Component
Use JSX in following format
```
class Test extends React.Component{
    render()
    {
        return(
            <h2>Testing React</h2>
        );
    }
}
``` 
### Props
```
class Board extends React.Component {
    renderSquare(i) {
        return <Square value={i}/>;
    }
    
render() {
        return (
            <button className="square">
                {this.props.value}
            </button>
        );
    }    
    
```    
### States
```
var Login = React.createClass({

    getInitialState:function()
    {
        return{checked:true}
    },
    render:function(){
            var msg;
            if(this.state.checked){msg='Ok alright';}
            else{msg='Not OK';}
            return(<div>{msg}</div>
            );
        }
});

```
