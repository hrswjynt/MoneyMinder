<script>
	import { page } from '$app/stores';
	let links = [
		{ name: 'Expense', url: '/activity/expense' },
		{ name: 'Income', url: '/activity/income' }
	];
	$: console.log($page);
</script>

<div class="fixed flex w-full flex-col items-center justify-center gap-y-3 bg-sky-500 py-3">
	<span class="text-xl font-bold text-white">Activity</span>
	<div class=" rounded-full bg-sky-800">
		{#each links as link}
			<a
				href={link.url}
				class="{$page.url.pathname == link.url
					? 'text-sky bg-white'
					: 'text-white'} rounded-full px-12 py-2 font-semibold transition-all duration-100"
			>
				{link.name}
			</a>
		{/each}
	</div>
</div>
