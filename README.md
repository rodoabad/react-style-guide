# React Style Guide

## Class vs. stateless

* Unless you will be using any of React's [lifecycle](https://facebook.github.io/react/docs/component-specs.html) methods, then always favor stateless function components over classes. Although there's no performance benefits when it comes to using stateless function components, what it offers is a cleaner look when writing your components.
* Always use a `const` and an arrow function for your stateless components. Arrow functions [preserve the `this` keyword](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions) so whenever you are inside your component, you are 100% sure that the `this` keyword is for that specific component.

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
```

```javascript
// Good
const MyComponent = () =>
  <div className='my-component'>
    {'Hello world'}
  </div>;
```
