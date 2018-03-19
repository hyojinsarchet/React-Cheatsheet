# Components

- Components let you split the UI into independent, reusable pieces, and think about each piece in isolation.
- Conceptually, components are like JavaScript functions. They accept arbitrary inputs (called “props”) and return React elements describing what should appear on the screen.
- React in MVC: can be thought of as the "Views" layer.
- F.I.R.S.T. Components:
  (Focused, Independent, Reusable, Small, Testable)

- Initial Setup:
$ npm i -g create-react-app
$ create-react-app blog-app
$ cd blog-app
$ code .
$ npm run start
view the app at http://localhost:3000

- A Very Basic Component:
// bring in React and Component instance from React
import React, {Component} from 'react'

// define our Hello component
class Hello extends Component {
  // what should the component render
  render () {
    // Make sure to return some UI
    return (
      <h1>Hello World!</h1>
    )
  }
}

export default Hello

- JSX:  
a language that compiles to Javascipt that allows us to write code that strongly resembles HTML. It is eventually compiled to lightweight JavaScript objects.

- Virtual DOM:
The Virtual DOM is a key piece of how React works.
Because of that, React can keep track of changes in the actual DOM by comparing different instances of the Virtual DOM.
It only updates the actual DOM with the necessary changes.

![components] (components-page(1).png)
