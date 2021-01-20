
React Concepts:
	1. Component
	2. State
	3. Props
	4. Stateful and Stateless concepts
	5. Hooks
	6. Lifecycles
	
	How to make Component ?
		Two Types
			1. Functional
			2. Class based
			
		Functional Component
		Class based component
		
		State: 
		Props:
		
		Container Component and Presentational Component  
		
	
<TextEditor /> 
	<Header />
		<HeaderLeft />
			<Button />
			<Button />
			<Button />
		<HeaderCenter />
			<Title />
		<HeaderRight />
			<Button />
			<Button />
			<Icon />
			<Icon />
			<Icon />
	<Body />
	<Footer />
		
		
		
import React, { Component } from "react";

export default function App() {
  const title = "This is a title text.";
  const age = 12;
  return (
    <div>
      <Header age={age} />
      {/* <Body title={title} title2="this is title2" />
      // <Button /> */}

      <Button title="Open" color="red"/> <br />
      <Button title="Close" color="pink" /><br />
      <Button title="Reset" color="orange" /><br />
    </div>
  );
}

function Button(props) {
  return (
    <div>
      <button style={{width:100,height:40, background:props.color, border:'none'}}> { props.title}</button>
    </div>
  );
}

 const Body = (props) => {
  return (
    <div>
      <h1> This is a Body </h1>
      <h3>
        {" "}
        {props.title} {props.title2}{" "}
      </h3>
      <p>THis is a paragraph</p>
    </div>
  );
};

class Header extends Component {
  state = {
    // hide: false,
    // title: "My App",
    count: 0,
    hide: false
  };

  incrementCount = () => {
    this.setState({
      count: this.state.count + 1,
      hide:true
    });
  };

  decrementCount = () => {
    this.setState({
      count: this.state.count - 1
    });
  };

  render() {
    return (
      <div>
        <ul>
          {/* <li>Home</li>
          <li>Services</li>
          <li>Contact</li>
          <p> The age of child is {this.state.age} </p> */}
          <h1> {this.state.count} </h1>
          <button onClick={this.incrementCount}> Increment </button>{" "}
          &nbsp;&nbsp;
          { !this.state.hide && <button onClick={this.decrementCount}> Decrement </button>}
        </ul>
      </div>
    );
  }
}
