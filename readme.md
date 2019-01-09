## React project setup from scratch

This project includes basic setup of react along with webpack and babel, there is no `create-react-app` is used for this.

Please make that you have Node.js v8.20 and npm v6.4.1 installed.

1. Make a empty folder and run the below command to generate the `package.json` file
   `npm init`

2. Now it's time to install the latest `React` and `React-dom`
   `npm i react react-dom`

3. Now it's time to add the Webpack, for this we need to run the below command
   `npm i --save-dev webpack webpack-cli webpack-dev-server`
   after the installation create a `webpack.config.js` file on the root of your project

4. Now it's time to install the babel dependecies
   `npm i --save-dev @babel/core @babel/preset-env @babel/preset-react babel-loader`

# Note

Add `.babelrc` file on the root of your project
`{ "presets": ["@babel/preset-env", "@babel/preset-react"] }`

## Quick start

1. Please make that you have Node.js v8.20 and npm v6.4.1 installed.
2. Clone this repo using git clone https://github.com/anujjangid/react-boilerplate.git
3. Install the dependencies using `npm install`
4. Start your project using `npm run start`

## Lifecycle Methods Overview
```Javascript 
componentWillMount() {
    // used to do all the necessary prepration for the component to render
    // never update state here
    console.log('trigger before render');
  }
  componentDidMount() {
    // All the Api call should be here
    console.log('trigger after render');
  }
  componentWillReceiveProps(nextProps) {
    // this lifecycle method is used to keep the state synced with update props
    if (this.props.status !== nextProps.status) {
      this.setState({
        status: nextProps.status,
      });
    }
    console.log('render if any prop value changed');
  }
  shouldComponentUpdate(nextProps, nextState) {
    let checkStatus = true;
    // return true if you want to re-render the component
    console.log('conditionally re-render the component');
    return checkStatus;
  }
  componentWillUpdate() {
    // this lifecycle method will only trigger when shouldComponentUpdate return true
    console.log('trigger before the re-render happen');
  }
  componentDidUpdate() {
    // this lifecycle method will only trigger after the render, only when shouldComponentUpdate return true
    console.log('trigger after the re-render happen');
  }
  componentWillUnmount() {
    // Last lifecycle method used  before the component actually removed from the dom
    // this method is used to clear all the things which are not required for the component, like timeout , session, logout
    console.log('trigger when component is unmount');
  }
```