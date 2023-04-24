# TextField

Sx version of (text based) input

## Usage
```markup
  <TextField type="text" on:change={(e)=>titel = e.detail.value}
             sx={{rounding: 2, float:1, minHeight:4, fontSize:2, textAlign:"center"}}
             value={titel}/>
   
```

## Properties
```properties
sx | sx styling | object
sxClass | sx class based styling | object
hover | sx hover styling | object
click | click event (also enter for usabillity) | cb -> ()=>{}
value | default value |string
type | type of input | string "text (default", "email", "password"

id | html id | string
```
