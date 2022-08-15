<script>
    import Button from "./Button.svelte";
    let variant = "text";
    let color = "primary";
    export { variant, color };
    const colors = {
            primary: { color:"#2476d2",rippleColor:"#9cc2e87a" },
            secondary: { color:"#a04cb0",rippleColor:"#bf7fcf7a" },
            success:{ color:"#467d32",rippleColor:"#2a58197a" },
            error:{ color:"#b70000",rippleColor:"#ff7f7f7a" }, 
            warning:{ color:"#fbd71e",rippleColor:"#ffbf7f7a" }, 
    };
</script>

<div>
    {#if variant === "text"}
        <Button
            on:click
            backgroundColor="transparent"
            borderColor="transparent"
            textDecoration="none"
            color={colors[color].color}
            fontWeight="normal"
            rippleColor={colors[color].rippleColor}
            texttransform="uppercase"
        >
            <slot />
        </Button>
    {:else if variant === "outline"}
        <Button
            on:click
            backgroundColor="transparent"
            borderColor={colors[color].color}
            textDecoration="none"
            fontWeight="normal"
            color={colors[color].color}
            rippleColor={colors[color].rippleColor}
            texttransform="uppercase"
        >
            <slot />
        </Button>
    {:else if variant === "contained"}
        <Button
            on:click
            backgroundColor="#2476d2"
            textDecoration="none"
            fontWeight="normal"
            color="#fff"
            rippleColor="#9cc2e87a"
            texttransform="uppercase"
        >
            <slot />
        </Button>
    {:else if variant === "disabled"}
        <Button
            backgroundColor="#e0e0e0"
            textDecoration="none"
            fontWeight="normal"
            color="#b6b6b6"
            ripple="false"
            texttransform="uppercase"
            disabled
        >
            <slot />
        </Button>
    {:else}
        <Button on:click texttransform="uppercase" fontWeight="normal">
            <slot />
        </Button>
    {/if}
</div>
<style>

</style>
