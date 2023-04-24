# Nav

Basic nav bar

## Usage
```markup
<Navbar links={["home", "contact", "FAQ"]} 
        color="orange" hover={{backgroundColor:"blue"}} 
        sx={{height:"15vh"}}/>

```

## Properties
```properties
sx | sx styling | object
sxClass | sx class based styling | object
hover | sx hover styling | object
color | bg color | string
links | name of links | string[]
to | custom link for name | string[] default->links
id | html id | string
```
