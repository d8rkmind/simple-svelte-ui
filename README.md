# Svelte Simple UI

To see a working demo of **simple-svelte-ui**

```bash
> npm install 
> npm run dev 
```

How to use

```svelte
<script>
 import {Button} from 'simple-svelte-ui'
</script>

<Button>Example 1</Button>
<Button
 backgroundColor="red"
>Example 2</Button>
```

## Button Options

| Options |Uses  |
|--|--|
|  backgroundColor| To change the background color|
|borderWidth|To change the border width of the button |
|borderStyle|To change the border line style of the button |
|borderColor|To change the border color of the button |
|borderRadius|To change the border radius of the button |
|color|To change the text color |
|cursor|To change the cursor type |
|fontSize|To change the font type|
|fontWeight|To change the font weight |
|padding| to add an internal paddin |
|textDecoration|To change the text Decoration |
|ripple|{boolean} To specify if a ripple effect is needed or not |
|rippleDuration|The ripple effect duration |
|rippleColor|The color of the ripple |
