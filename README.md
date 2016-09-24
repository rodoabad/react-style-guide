# React Style Guide

## Class vs. stateless

* Unless you will be using any of React's [lifecycle](https://facebook.github.io/react/docs/component-specs.html) methods, then always favor stateless function components over classes. Although there's no performance benefits when it comes to using stateless function components, what it offers is a cleaner look when writing your components.
* Always use a `const` and an arrow function for your stateless components. Arrow functions [preserve the `this` keyword](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) so whenever you are inside your component, you are 100% sure that the `this` keyword is for that specific component.
* The component should always be on the next line after your arrow function.

```javascript
// Bad
function MyComponent() {
  return (
    <div className='my-component'>
      {'Hello world'}
    </div>
    );
}

// Bad
class MyComponent extends Component {
  render() {
    return (
      <div className='my-component'>
        {'Hello world'}
      </div>;
      );
  }
}

// Bad
const MyComponent = () => <div className='my-component'>
    {'Hello world'}
  </div>;
```

```javascript
// Good
const MyComponent = () =>
  <div className='my-component'>
    {'Hello world'}
  </div>;
```

## Naming Convention

* Always use `.js` as your extension instead of `.jsx`
* Use lowercase and hypens for react component file names e.g. `my-component.js`

* Use camelCase for instances

```javascript
// Bad
const MyComponent = <MyComponent/>;

const my-component = <MyComponent/>;
```

```javascript
// Good
const myComponent = <MyComponent/>;
```

* Use PascalCase for React components

```javascript
// Bad
import myComponent from './my-component';

import my-component from './my-component';
```

```javascript
// Good
import MyComponent from './my-component';
```

## Declaration

* Always use a `displayName` when naming your components.
* It should have the same name as your arrow function.
* It should always be located immediately after your class or stateless component and separated by a new line.
```javascript
// Bad
const MyComponent = () =>
  <div className='my-component'>
    {'Hello world'}
  </div>;
MyComponent.displayName = 'MyComponent';

// Bad
const MyComponent = () =>
  <div className='my-component'>
    {'Hello world'}
  </div>;

MyComponent.displayName = 'AnotherName';
```

```javascript
// Good
const MyComponent = () =>
  <div className='my-component'>
    {'Hello world'}
  </div>;
  
MyComponent.displayName = 'MyComponent';
```

* The top level element for your component should always have a `className` with the same name as your component separated by hyphens and in lowercase.

```javascript
// Bad
const MyComponent = () =>
  <div>
    {'Hello world'}
  </div>;
  
// Bad
const MyComponent = () =>
  <div className='myComponent'>
    {'Hello world'}
  </div>;
  
// Bad
const MyComponent = () =>
  <div className='MyComponent'>
    {'Hello world'}
  </div>;
  
// Bad
const MyComponent = () =>
  <div className='my_component'>
    {'Hello world'}
  </div>;
```

```javascript
// Good
const MyComponent = () =>
  <div className='my-component'>
    {'Hello world'}
  </div>;
```
