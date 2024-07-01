<script lang="ts">
	import EditThing from './EditThing.svelte';
	import Modal from '$lib/components/Modal.svelte';

	export let obj: any;
	export let onHide;
	$: isEditing = !!obj;
</script>

<Modal isOpen={isEditing} {onHide}>
	{#if obj}
		<EditThing {obj} />
	{/if}
</Modal>
