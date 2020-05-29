# Knockout

## HTML

```markup
<input data-bind = "value: "></input>

<button></button>  
<input></input> // Value
<select></select> // Options

<Value: $<span />/>
```

## Knockout

### General

`data-bind = "<data type> <data>`

Observables: properties that automatically issues notifications when changed

`ko.observable("")`: properties that will update

Computed Properties

`ko.computed(function() { ... })`

`"click: ..."`  
`"text: ..."`  
`"value: ..."`

`foreach: ..."`

`options: ..., value: ..., optionsText: ...`

* `options`: `[1,2,3,4,5...]`

Interactivity

`visible: ...`  
`enable: ...`

Custom Binding

`ko.bindingHandlers`

* `init`: called when binding first happens
* `update`: when associated data updates

General

`$root.`

```javascript
function() {
    return this.<field>() + this.field();
}, this);

.toFixed() // Rounds digits
```

### Ajax

`$.getJSON`  
`$.ajax`

`.destroy`

### Single page applications

`"with: ..."`: creates a binding context used to bind elements inside

