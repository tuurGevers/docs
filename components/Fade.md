# Fade

component for fade from transition directive

## Usage
```javascript
<Fade duration={2000} delay={1000} instant>
    <Image src="favicon.png" alt="foto" sx={{width:{lg:"50%", sm:"100%"}, height:"auto", maxHeight:"400px"}}/>
</Fade>
```

## Properties
```properties
dir | direction | string "x"/"y"
amount | amount of pixels | number
duration | amount of ms | number
delay | delay in amount of pixels | number
instant | desides if animation starts on load or on view | Boolean
```
