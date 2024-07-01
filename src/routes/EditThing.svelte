<script lang="ts">
	import Input from '$lib/form/Input.svelte';
	import InputGroup from '$lib/form/InputGroup.svelte';

	export let obj: any;

	const updateObj = (updates: any) => {
		obj = { ...obj, ...updates };
	};
</script>

<div class="sm:col-span-2 grid grid-cols-3 gap-x-5 gap-y-4">
	<h1>Editing</h1>
	<button on:click={() => updateObj({ things: [...obj.things, ''] })}>Add</button>
	{#each obj.things || [] as str, index (index)}
		<InputGroup labelText="a">
			<Input bind:value={str} />
		</InputGroup>
	{/each}
</div>
