<script lang="ts">
	export let error = false;

	let className = '';
	export { className as class };

	const { className: ignore, ...rest } = $$restProps;

	export let inputEl: HTMLInputElement = null as any;

	export let value: string = '';
	export let size: 'sm' | 'default' = 'default';
</script>

<input
	on:blur
	on:change
	on:input
	on:keydown
	class:border-neutral-400={!error}
	class:border-danger-5={error}
	class:focus:shadow-md={!error}
	class:focus:shadow-sm={error}
	class:focus:shadow-danger-7={error}
	class:h-8={size === 'sm'}
	class:h-9={size === 'default'}
	class="bg-white text-neutral-600 border rounded py-1 px-3 text-base block w-full transition-box-shadow {className}"
	bind:this={inputEl}
	bind:value
	{...rest}
/>
