<script lang="ts">
	export let obj: any;

	const updateObj = (updates: any) => {
		obj = { ...obj, ...updates };
	};
</script>

<div class="sm:col-span-2 grid grid-cols-3 gap-x-5 gap-y-4">
	<h1>Editing</h1>
	<button on:click={() => updateObj({ things: [...obj.things, ''] })}>Add</button>
	{#each obj.things || [] as str, index (index)}
		<input bind:value={str} />
	{/each}
</div>
