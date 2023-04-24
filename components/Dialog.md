# Dialog

Sx version Modal

## Usage
```markup
<Button click={()=>open=!open}>open dialog</Button>
<Dialog open={open} on:outside={()=>open=false}>
    <Typography>hello dialog</Typography>
</Dialog>
```

## Properties
```properties
sx | sx styling | object
sxClass | sx class based styling | object
hover | sx hover styling | object
click | click event (also enter for usabillity) | cb -> ()=>{}
open | controls state of dialog | Boolean
on:outside | eventhandler for outside click| cb -> ()=>{}
id | html id | string
```
