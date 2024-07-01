<script lang="ts">
	import * as AlertDialog from '$lib/components/ui/alert-dialog';

	export let isOpen: boolean;
	export let onHide: () => void;
	export let openFocus: HTMLElement | null = null;

	function onChange(open: boolean) {
		if (!open) {
			onHide();
		}
	}

	$: {
		if (isOpen) {
			onChange(true);
		}
	}

	let el: HTMLDivElement;

	$: {
		if (el) {
			el.addEventListener('click', onHide);
		}
	}
</script>

<AlertDialog.Root openFocus={() => openFocus} bind:open={isOpen} closeOnOutsideClick={false}>
	<AlertDialog.Trigger asChild let:builder />

	<AlertDialog.Content bind:el class="translate-y-[0] top-16 pb-5">
		<AlertDialog.Header>
			<AlertDialog.Title>Modal <button on:click={onHide}>Close</button></AlertDialog.Title>
		</AlertDialog.Header>
		<AlertDialog.Description>
			<slot />
		</AlertDialog.Description>
	</AlertDialog.Content>
</AlertDialog.Root>
