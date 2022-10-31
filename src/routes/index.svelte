<script>
	import { getContext } from "svelte";
	import Demo from "$components/demo/Demo.svelte";
	import WIP from "$components/helpers/WIP.svelte";
	import Cup from "$components/Cup.svelte";
	import Footer from "$components/Footer.svelte";

	const copy = getContext("copy");
	// const data = getContext("data");
</script>

<Cup />
<Footer />
