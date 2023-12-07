<script>
	import { page } from '$app/stores';

	const links = [
		{ title: 'Home', icon: 'home', url: '/' },
		{ title: 'Activity', icon: 'receipt', url: '/activity' },
		{ title: 'History', icon: 'chart-simple', url: '/history' },
		{ title: 'Settings', icon: 'gear', url: '/settings' }
	];

	$: currentPage = $page.url.pathname;
	$: console.log(currentPage);
	console.log('/activity/expense'.split('/').filter((string) => string != ''));
</script>

<div class="fixed bottom-0 flex w-full items-end justify-around bg-white shadow-inner">
	{#each links as link}
		<a
			href={link.url}
			class="hover:bg-100 flex w-full flex-col items-center gap-1 pb-1 pt-3
			{currentPage.includes(link.url) ? 'text-sky-500' : 'text-gray-500'} transition-all duration-100"
		>
			<i class="fa fa-{link.icon} text-2xl"></i>
			<span class="font-semibold">{link.title}</span>
		</a>
	{/each}
</div>
