<script>
	import Button from "./lib/button/Button.svelte";
	function click() {
		alert("clicked");
	}

</script>
<svelte:head>
	<title>Svelte Beautify</title>
</svelte:head>
<Button on:click={click}>Hello</Button>