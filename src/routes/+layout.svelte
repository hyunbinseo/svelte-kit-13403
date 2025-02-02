<script lang="ts">
	import { goto } from '$app/navigation';
	import { page } from '$app/state';

	const { children } = $props();
</script>

<span>current: {page.url.pathname}</span>

<ul>
	{#each ['/a', '/b'] as path, index}
		<li>
			<button onclick={() => goto(path, { replaceState: true })}>
				goto {path}
			</button>
			<span>- history entry is {!index ? 'not added' : 'added'}</span>
		</li>
	{/each}
</ul>

{@render children()}
