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

### Dynamically add and remove components
This is done by maintaining an array of the states of the components. For deletion we reference the child index by passing function as a prop to it.
```
var TestComponent = React.createClass({
   remove:function(){
     this.props.deleteComponent(this.props.index);
   },

   render:function(){
       return(
           <button className="btn btn-danger" onClick={this.remove} value="Remove">Remove</button>
       );
   }
});

var Login = React.createClass({
    getInitialState:function(){
        return{
            comments:[]
        }
    },
    removeButton:function(i){
        var arr = this.state.comments;
        arr.splice(i,1);
        this.setState({comments:arr});
    },
    addButton:function(text){
        var arr = this.state.comments;
        arr.push(text);
        this.setState({comments:arr});
    },
    createButton:function(text,i){
        return(
            <TestComponent key={i} index={i} deleteComponent={this.removeButton}>{text}</TestComponent>
        );
    },
    render:function(){
            return(
                <div>
                    <input type="button" onClick={this.addButton.bind(null,"Defaultwa")} className="btn btn-info" value="Add"/>
                    {this.state.comments.map(this.createButton)}
                </div>
            );
        }
});

```
