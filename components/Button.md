# Button

Sx version of button

## Usage
```markup
<Button sx={{width:{sm:5, lg:20}}}
            hover="{{backgroundColor:{sm:"green", lg:"red"}}} click={()=>alert("test")}">
        test
    </Button>
```

## Properties
```properties
sx | sx styling | object
sxClass | sx class based styling | object
hover | sx hover styling | object
click | click event (also enter for usabillity) | cb -> ()=>{}
id | html id | string
```
