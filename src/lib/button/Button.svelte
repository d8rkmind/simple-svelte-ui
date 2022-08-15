<script>
    let backgroundColor = "#fff";
    let borderWidth = "1px";
    let borderStyle = "solid";
    let borderColor = "#ccc";
    let borderRadius = "5px";
    let color = "#000";
    let cursor = "pointer";
    let fontSize = "1em";
    let fontWeight = "bold";
    let padding = "10px";
    let textDecoration = "none";
    let rippleColor = "rgba(102, 102, 102, 0.274)";
    let rippleDuration = "200ms";
    let ripple ="true";
    let texttransform = "none";
    export {
        ripple,
        rippleColor,
        rippleDuration,
        textDecoration,
        padding,
        fontWeight,
        fontSize,
        color,
        cursor,
        borderRadius,
        borderColor,
        borderStyle,
        borderWidth,
        backgroundColor,
        texttransform
    };
</script>

<div
    style="--bgbutton:{backgroundColor};--buttonborderThickness:{borderWidth};--buttonborderStyle:{borderStyle};--buttonborderColor:{borderColor}
    ;--buttonborderRadius:{borderRadius}; --buttoncolor:{color}; --buttoncursor:{cursor}; --buttonfontSize:{fontSize}; --buttonfontWeight:{fontWeight};
    --buttonpadding:{padding}; --buttontextDecoration:{textDecoration}; --buttonrippleColor:{rippleColor}; --buttonrippleDuration:{rippleDuration}
    ;--buttonripple:{ripple =='true' ? 1 : 0}; --buttontexttransform:{texttransform};"
>
    <button class="btn" on:click><slot /></button>
</div>

<style>
    .btn {
        background-color: var(--bgbutton);
        border: var(--buttonborderThickness) var(--buttonborderStyle)
            var(--buttonborderColor);
        border-radius: var(--buttonborderRadius);
        color: var(--buttoncolor);
        cursor: var(--buttoncursor);
        display: inline-block;
        font-size: var(--buttonfontSize);
        font-weight: var(--buttonfontWeight);
        margin: 5px;
        padding: var(--buttonpadding);
        text-align: center;
        text-decoration: var(--buttontextDecoration);
        transition: all 0.3s ease-in-out;
        position: relative;
        text-transform: var(--buttontexttransform);
    }
    .btn::before {
        content: "";
        position: absolute;
        inset: 0;
        transform: scaleX(0);
        width: 100%;
        height: 100%;
        background-color: var(--buttonrippleColor);
        border-radius: 5px;
        transform-origin: center;
    }
    .btn:active::before {
        animation: ripple var(--buttonrippleDuration)
            cubic-bezier(0.23, 1, 0.32, 1);
    }
    @keyframes ripple {
        to {
            transform: scaleX(var(--buttonripple));
        }
    }
</style>
