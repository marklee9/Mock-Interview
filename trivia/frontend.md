# Frontend Trivia
## General
___

<br/>

What are two-way data binding and one-way data flow, and how are they different?

    This a tough-y 😎. Here's the deal: Two-way data binding means that UI fields are bound to model data dynamically. 
    
    I.e., when a UI field changes, the model data changes with it and vice-versa. 
    
    An example of this is Angular.js, which uses two-way binding. 
    
    One way data flow means that the model is the single source of truth. A change in UI is not directly bound to the model. An example of a one-way data flow framework is React. Only the model, or store in this case, has access to the application's state.


<br/>
<br/>

## HTML

<br/>

___

<br/>

What does DOCTYPE do?

    DOCTYPE is an abbreviation for DOCument TYPE.
    A DOCTYPE is always associated to a DTD - for Document Type Definition.

    A DTD defines how documents of a certain type should be structured,
    whereas a DOCTYPE declares what DTD a document supposedly respects.


<br/>

___

<br/>

## CSS


What does float do?

    Float removes the element from the normal flow of the document and pushes the element to the sides of the page with text wrapping around it.


<br/>

___

<br/>

Display properties

    Display : inline
      Displays an element as an inline element (like <span>). 
      Any height and width properties will have no effect.

    Display : block
      Displays an element as a block element (like <p>). 
      It starts on a new line, and takes up the whole width.

    Display : inline-block
      Displays an element as an inline-level block container. 
      The element itself is formatted as an inline element, but you can apply height and width values.

    Display : none
      The element is completely removed.

<br/>

___

<br/>

Name few pseudo selectors 

    :hover,     :nth-of-type,     :visited,
    :focus,     :link,            :first, 
    :child,     :checked,         :last-child,
    :target.

## React

<br/>

___

<br/>

Does React require JSX?

        It is not necessary but it is very useful. But it is very convenient.

        Each JSX element is just syntactic sugar for calling 
        React.createElement(component, props, ...children)

```js
// Using JSX.
class Hello extends React.Component {
  render() {
    return <div>Hello {this.props.toWhat}</div>;
  }
}

ReactDOM.render(
  <Hello toWhat="World" />,
  document.getElementById('root')
);
```
```js
// Not using JSX.
class Hello extends React.Component {
  render() {
    return React.createElement('div', null, `Hello ${this.props.toWhat}`);
  }
}

ReactDOM.render(
  React.createElement(Hello, {toWhat: 'World'}, null),
  document.getElementById('root')
);
```


