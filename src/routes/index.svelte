<script lang="ts">
	import { browser } from '$app/env';

	interface IDictionary {
		name: string;
		public: boolean;
		entryCount: number;
	}

	import Collection from 'sveltefirets/components/Collection.svelte';
	let dictionariesType: IDictionary[] = [];
</script>

Here are the dictionaries <br />
{#if browser}
	<Collection path="chats" startWith={dictionariesType} let:data={dictionaries}>
		{#each dictionaries as dictionary}
			{dictionary.name}
		{/each}
	</Collection>
{/if}
