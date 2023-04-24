# TextUtil

Minimalistic tool for bloggers 

## Usage
```markup
<TextUtil lines={8} modes={"all"} 
on:valueChange={(e)=>tekst=e.detail.value} 
value={tekst} sx={{width:"90%"}}/>
```

## Properties
```properties
sx | sx styling | object
sxClass | sx class based styling | object
value | default value |string
modes | modes u want to use | string["bold", "italic", "underline", "strikethrough", "sup", "sub", "link"]
lines | number of lines | number
on:valueChange | cb for on input and mode click | cb -> ()=>{}
id | html id | string
```
