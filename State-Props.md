# Props and States

## props
- Properties! Every component has .props
- Immutable
- We define properties in development and pass them in as attributes to the JSX element in our .render method.


- Ex 1)
src/index.js
(pass multiple properties to our component)

import React from 'react';
import ReactDOM from 'react-dom'
import Hello from './App.js'

ReactDOM.render(
  <Hello name={"Nick"} age={24} />,
  document.getElementById('root')
)

src/Hello.js
(definition we have access to both values)

class Hello extends Component {
  render () {
    return (
      <div>
        <h1>Hello {this.props.name}</h1>
        <p>You are {this.props.age} years old</p>
      </div>
    )
  }
}

- Ex 2)
src/Comment.js

import React, {Component} from 'react'

class Comment extends Component {
  render () {
    return (
      <div>
        <p>{this.props.message}</p>
      </div>
    )
  }
}

export default Comment

src/App.js
(load in our Comment component and render it inside of our Post component)

import React, { Component } from 'react';
// Load in Comment component
import Comment from './Comment.js'

class Post extends Component {
  render() {
    return (
      <div>
        <h1>{this.props.title}</h1>
        <p>By {this.props.author}</p>
        <div>
          <p>{this.props.body}</p>
        </div>
        <h3>Comments:</h3>
        // Render Comment component, passing in data
        <Comment message={this.props.comments[0]} />
      </div>
    );
  }
}

export default Post;


(using .map to avoid having to hard-code all of our Comments)
class Post extends Component {
  render() {
    let comments = this.props.comments.map((comment, index) => (
      <Comment message={comment} key={index}/>
    ))
    return(
      <div className='post-page'>
        <h1>{this.props.title}</h1>
        <h2>By {this.props.author}</h2>
        <p>{this.props.body}</p>

        <h3>Comments</h3>
        {comments}
      </div>
    )
  }
}



## States

- Local or native to the component
  (props are passed into a component)
- Mutable
- Ex)

class Clock extends React.Component {
  constructor(props) {
    super(props);
    this.state = {date: new Date()};
  }

  render() {
    return (
      <div>
        <h1>Hello, world!</h1>
        <h2>It is {this.state.date.toLocaleTimeString()}.</h2>
      </div>
    );
  }
}

ReactDOM.render(
  <Clock />,
  document.getElementById('root')
);
