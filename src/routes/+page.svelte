<script lang="ts">
	import Modal from '$lib/components/Modal.svelte';
	import HandleThing from './HandleThing.svelte';
	import ThingModal from './ThingModal.svelte';

	const createEmpty = () => {
		return {
			things: ['']
		};
	};

	let obj: any = null;

	const reset = () => (obj = createEmpty());
</script>

<button on:click={reset}>Do it</button>

<ThingModal {obj} onHide={() => (obj = null)} />
