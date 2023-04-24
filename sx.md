

# Styler Class Documentation

The `Styler` class is a JavaScript class that allows creating CSS styles dynamically with support for responsive design. It also includes special properties that are translated into CSS code.

## Properties

- `styling`: A string representing the current CSS style of the object.
- `sm`: A string representing the CSS style for screen sizes smaller than 640 pixels.
- `md`: A string representing the CSS style for screen sizes between 640 and 768 pixels.
- `lg`: A string representing the CSS style for screen sizes between 768 and 1024 pixels.
- `global`: A string representing the CSS style that is applied to all screen sizes.

## Methods

- `constructor()`: Initializes the properties of the Styler object.
- `async createStyle(sx: object, sxClass?: object[])`: Creates CSS styles based on the `sx` object and `sxClass` arrays passed as arguments. `sx` represents the default style, and `sxClass` represents the additional styles. The `createStyle` method also sets the `global`, `sm`, `md`, and `lg` properties of the Styler object.
- `containsUppercase(str: string)`: Returns `true` if the `str` parameter contains any uppercase letters, otherwise `false`.
- `selectStyle(width?: number)`: Returns the CSS style for the specified screen size. If the `width` parameter is not provided, the method returns the current global style.
- `checkSpecial(key: string, value: any)`: Translates a special `key` property into its corresponding CSS code and returns a tuple containing the translated string and a `valid` flag. The `value` parameter represents the value of the `key` property.

## Special Properties

The following special properties are supported by the Styler class and translated into CSS code:

- `rounding`: Specifies the border radius of an object. The value is multiplied by 8 pixels.
- `backgroundRepeat`: Specifies how a background image is repeated.
- `backgroundSize`: Specifies the size of a background image.
- `backgroundPosition`: Specifies the position of a background image.
- `float`: Specifies a shadow effect for an object. The value is multiplied by 8 pixels.
- `flex`: Specifies the flex direction of a container. The value can be either "row" or "col".
- `flexAlign`: Specifies the alignment of the flex items inside a container. The value can be either "center" or "around".
- `margin` or `m`: Specifies the margin of an object.
- `marginTop` or `mt`: Specifies the top margin of an object.
- `marginRight` or `mr`: Specifies the right margin of an object.
- `marginBottom` or `mb`: Specifies the bottom margin of an object.
- `marginLeft` or `ml`: Specifies the left margin of an object.
- `padding` or `p`: Specifies the padding of an object.
- `paddingTop` or `pt`: Specifies the top padding of an object.
- `paddingRight` or `pr`: Specifies the right padding of an object.
- `paddingBottom` or `pb`: Specifies the bottom padding of an object.
- `paddingLeft` or `pl`: Specifies the left padding of an object.

## Example Usage

```javascript
<script lang="ts">
    import {afterUpdate, onMount} from "svelte";
    import {Styler} from "../script/utils";
    import {hover} from "../script/hover";
    import Skeleton from "./Skeleton.svelte";

    let width = 0;
    let styling = "";
    let permaStyle = "";
    let hoverStyle = "";
    let props = {...$$restProps};

    const stylor = new Styler();
    const hoverStylor = new Styler();

    $: if (width) {
        assignStyle();
    }

    onMount(async () => {
        if (props.hover) {
            await hoverStylor.createStyle(props.hover);
        }
    });

    afterUpdate(() => {
        assignStyle();
    });

    function assignStyle() {
        styling = stylor.selectStyle(width);

        if (props.extra) {
            styling += " " + props.extra;
        }

        if (props.hover) {
            styling += " " + hoverStyle;
        }

        permaStyle = styling;
    }

    function handleHover() {
        if (props.hover) {
            hoverStyle = hoverStylor.selectStyle(width);
            assignStyle();
        }
    }

    function handleLeave() {
        if (props.hover) {
            hoverStyle = "";
            assignStyle();
        }
    }

    export let sx: Record<string, unknown> = {};
</script>

{#await stylor.createStyle(sx, props.sxClass)}
    <Skeleton rows={5}/>
{:then _}
    <p style={styling} on:click={props.click} on:keypress={(e)=>e.key==="Enter"?props.click:""} class={props.class} id={props.id} use:hover on:hover={(e)=>handleHover(e)}
       on:leave={()=>handleLeave()}>
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore
        magna
        aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea<br/> commodo
        consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla
        pariatur.
        Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
    </p>
{/await}

<svelte:window bind:innerWidth={width}/>
