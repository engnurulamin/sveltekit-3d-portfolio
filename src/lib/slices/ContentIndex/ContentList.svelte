<script lang="ts">
	import { type Content, type ImageField, type KeyTextField } from '@prismicio/client';
	import { PrismicLink } from '@prismicio/svelte';
	import IconArrow from '~icons/ic/baseline-arrow-outward';
	export let items: Content.BlogpostDocument[] | Content.ProjectDocument[];
	export let fallbackItemImage: ImageField;
	export let viewMoreText: KeyTextField = 'Read More';
</script>

<ul>
	{#each items as post, index (post.id + index)}
		<li>
			<PrismicLink
				document={post}
				class="flex flex-col justify-between border-t border-t-slate-100 py-10 text-slate-200 md:flex-row"
			>
				<div class="flex flex-col">
					<span class="text-3xl font-bold">{post.data.title}</span>
					<div class="flex gap-3 text-yellow-400">
						{#each post.tags as tag}
							<span class="text-lg font-bold">
								{tag}
							</span>
						{/each}
					</div>
				</div>
				<span class="ml-auto flex items-center gap-2 text-xl font-medium md:ml-0">
					{viewMoreText}
					<IconArrow />
				</span>
			</PrismicLink>
		</li>
	{/each}
</ul>
