<script lang="ts">
	import Modal from '$lib/components/Modal.svelte';
	import HandleThing from './HandleThing.svelte';

	export let obj: any;
	export let onHide;
</script>

<Modal isOpen={!!obj} {onHide}>
	<HandleThing {obj} />
</Modal>
