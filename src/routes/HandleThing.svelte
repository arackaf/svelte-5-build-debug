<script lang="ts">
	import EditThing from './EditThing.svelte';

	export let obj: any;
</script>

{#if obj}
	<EditThing {obj} />
{/if}
