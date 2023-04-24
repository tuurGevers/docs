# TextArea

Sx version of textarea

## Usage
```markup
<TextArea on:change={(e)=>message = e.detail.value}
          sx={{width:"60%",height:`10em`,p:4, fontSize:3, float:1, rounding:2, resize:"none", mb:4}}/>
```

## Properties
```properties
sx | sx styling | object
sxClass | sx class based styling | object
hover | sx hover styling | object
click | click event (also enter for usabillity) | cb -> ()=>{}
on:selection | cb function on text selection | cb -> ()=>{}
on:enter | cb function on enter press | cb -> ()=>{} 
value | default value |string
id | html id | string
```
