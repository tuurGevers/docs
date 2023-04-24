# Box

Sx version of sectioning

## Usage
```markup
<Box variant={Variants.DIV} sxClass={[boxStyles.paper()]} sx={{zIndex:"2"}}>
    <Typography variant={1}>Hello World</Typography>
</Box> 
```

## Properties
```properties
sx | sx styling | object
sxClass | sx class based styling | object
hover | sx hover styling | object
click | click event (also enter for usabillity) | cb -> ()=>{}
variant | section variant | SectionVariants: 
    DIV,
    ARTICLE,
    ASIDE,
    FOOTER,
    HEADER,
    MAIN,
    NAV,
    SECTION,
id | html id | string
```
