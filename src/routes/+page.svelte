<script lang="ts">
	import HandleThing from './HandleThing.svelte';

	const createEmpty = () => {
		return {
			things: ['']
		};
	};

	let obj: any = null;

	const reset = () => (obj = createEmpty());
</script>

<button on:click={reset}>Do it</button>

<HandleThing {obj} />
