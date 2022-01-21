1. working with Props
    - [ ] getting props by name
    - [ ] destructuring props
``` js
function App(){
    const person = 'Moses';

    return (
        <div>
            <MyComp name={person} />
        </div>
    );
}

function MyComp(props){
    return (
        <div>
            <h1>{props.name}</h1>
        </div>
    )
}
```

2. class component state
``` js
class App extends React.Component{
  constructor(props){
    super(props);

    this.state = {
      people: [
        {id: 1, name: 'Moses'},
        {id: 2, name: 'Gbemu'}
      ]
    }
  }

  render(){
    return (
      <div>
        {
        this.state.people.map(person => {
          return (
            <div key={person.id}>
              <h1>{person.name}</h1>
            </div>
          )
        })
        }
      </div>
    )
  }
}
```

3. lifecycle

``` js
import { Component } from "react";

class App extends Component {
  constructor(props) {
    super(props);

    this.state = {
      time: 0
    };

    this.stopTime = this.stopTime.bind(this);
  }

  componentDidMount() {
    this.timerID = setInterval(() => this.tickTime(), 1000);
  }

  componentWillUnmount() {
    clearInterval(this.timerID);
  }

  tickTime() {
    this.setState((prevState) => ({
      time: prevState.time + 1
    }));
  }

  stopTime() {
    clearInterval(this.timerID);
  }

  render() {
    return (
      <div>
        {this.state.time}
        <button onClick={this.stopTime}> Stop </button>
      </div>
    );
  }
}

export default App;
```


4. events
``` js
class App extends React.Component {
    constructor(props){
        super(props);

        this.state = {
            person = "Gbemu";
        }
    }

    render(){
        return(
            <div>
                <h1>{this.state.person}</h1>
            </div>
        )
    }
}
```

``` js
// user input
import React, {Component} from 'react';

class App extends Component {
  constructor(props) {
    super(props);

    this.state = {
      person: ""
    };

    this.handleChange = this.handleChange.bind(this);
  }

  handleChange(e) {
    this.setState({
      person: e.target.value
    });
  }

  render() {
    return (
      <div>
        <input
          type="text"
          value={this.state.person}
          onChange={this.handleChange}
        />
        <button onClick={() => console.log(this.state.person)}> Click </button>
      </div>
    );
  }
}
```