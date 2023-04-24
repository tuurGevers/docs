# Select

Sx selection menu

## Usage
```text
<Select items={["nl", "es", "en"]} 
selected="es" on:change={(e)=>alert(e.detail.value)}/>

```

## Properties
```properties
sx | sx styling | object
sxClass | sx class based styling | object
hover | sx hover styling | object
selected | wich element is default | string
items | all items | string[]
on:change | cb on select | cb -> ()=> {}
id | html id | string
```
