# CheckBox

checkbox helper component

## Usage
returns an array of all selected elements eg:["1","3"] 
(may need some checking for null/undefined)
```markup
<CheckBox boxes={["1", "2", "3"]}
 on:checked={(e)=>console.log(e.detail.value)}/>
```

## Properties
```properties
styling is set on the input element
so styling is limited

sx | sx styling | object
sxClass | sx class based styling | object
hover | sx hover styling | object
boxes | all input elements | string[]
id | html id | string
```
