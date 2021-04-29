# Class-04 reading Summary

## Forms

You add a form with React like any other element.
```
class MyForm extends React.Component {
  render() {
    return (
      <form>
        <h1>Hello</h1>
        <p>Enter your name:</p>
        <input
          type="text"
        />
      </form>
    );
  }
}
ReactDOM.render(<MyForm />, document.getElementById('root'));
```

![form](https://d585tldpucybw.cloudfront.net/sfimages/default-source/default-album/form.png?sfvrsn=4b2b3473_0)


### Handling Forms

* Handling forms is about how you handle the data when it changes value or gets submitted.

* In HTML, form data is usually handled by the DOM.

* In React, form data is usually handled by the components.

* When the data is handled by the components, all the data is stored in the component state.

* You can control changes by adding event handlers in the onChange attribute.

### Submitting Forms
You can control the submit action by adding an event handler in the onSubmit attribute.



