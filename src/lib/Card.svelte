<script lang="ts">
	let {
		title,
		content,
		linkUrl,
		linkText,
		children
	}: {
		title?: string;
		content?: string;
		linkUrl?: string;
		linkText?: string;
		children?: any;
	} = $props();
</script>

<!-- conditional -->

<div
	class="flex max-w-md flex-col gap-3 rounded-lg bg-white p-3 shadow-md transition-shadow duration-300 hover:shadow-lg"
>
	{#if children}
		{@render children()}
	{/if}

	{#if !children}
		<h2 class="mb-4 text-2xl font-semibold text-gray-800">{{ title }}</h2>
		<p class="text-gray-600">{{ content }}</p>
		<a href={linkUrl} class="mt-4 inline-block font-semibold text-blue-500 hover:text-blue-700"
			>{{ linkText }}</a
		>
	{/if}
</div>
