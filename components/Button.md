# Button

Sx version of button

## Usage
```markup
<Button sx={{height:{sm:"80vh", md:"40vh", lg:"20vh"}, "background-color":"red", rounding:{sm:1, lg:2}, float:2}}
            hover={{backgroundColor:{sm:"green", lg:"red"}}} click={()=>alert("test")}>
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
