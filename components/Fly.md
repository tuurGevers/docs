# Fly

component for fly from transition directive

## Usage
```text
<Fly dir="y" amount="3000" duration={2000}>
    <Image src="favicon.png" alt="foto" sx={width:{lg:"50%", sm:"100%"}, height:"auto", maxHeight:"400px"}/>
</Fly>
```

## Properties
```properties
dir | direction | string "x"/"y"
amount | amount of pixels | number
duration | amount of ms | number
delay | delay in amount of pixels | number
instant | desides if animation starts on load or on view | Boolean
```
