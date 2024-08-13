<script lang="ts">
	import Bounded from '$lib/components/Bounded.svelte';
	import Heading from '$lib/components/Heading.svelte';
	import { skills } from '$lib/data/skills';
	import type { Content } from '@prismicio/client';
	import { PrismicRichText } from '@prismicio/svelte';

	export let slice: Content.ExperienceSlice;
</script>

<!-- <Bounded data-slice-type={slice.slice_type} data-slice-variation={slice.variation}>
	<Heading tag="h2" size="lg">{slice.primary.heading}</Heading>
	{#each slice.primary.item as item}
		<div class="ml-6 mt-8 max-w-prose md:ml-12 md:mt-16">
			<Heading tag="h3" size="sm">
				{item.title}
			</Heading>

			<p
				class="mt-1 flex w-fit items-center gap-1 text-2xl font-semibold tracking-light text-slate-400"
			>
				<span>{item.time_period}</span>
				{' '}
				<span class="text-3xl font-extralight">/</span>{' '}
				<span>{item.institution}</span>
			</p>
			<div class="prose prose-lg prose-invert mt-4">
				<PrismicRichText field={item.description} />
			</div>
		</div>
	{/each}
</Bounded> -->

<Bounded data-slice-type={slice.slice_type} data-slice-variation={slice.variation}>
	<div class="container mx-auto px-4 py-8 grid grid-cols-1 md:grid-cols-2 gap-8">
		<div class="flex flex-col p-8 text-slate-400">
			<Heading tag="h2" size="md">{slice.primary.heading}</Heading>
			{#each slice.primary.item as item}
				<div class="ml-6 mt-8 max-w-prose md:ml-12 md:mt-16">
					<Heading tag="h3" size="sm" class="border-b-2 border-slate-400 pb-2 mb-2">
						{item.title}
					</Heading>

					<p
						class="mt-1 flex w-fit items-center gap-1 text-2xl font-semibold tracking-light text-slate-400"
					>
						<span>{item.time_period}</span>
						{' '}
						<span class="text-3xl font-extralight">/</span>{' '}
						<span>{item.institution}</span>
					</p>
					<div class="prose prose-lg prose-invert mt-4">
						<PrismicRichText field={item.description} />
					</div>
				</div>
			{/each}
		</div>

		<div class="flex flex-col p-8 text-slate-400">
			<Heading tag="h2" size="md">Tech I Use</Heading>
			<div class="ml-6 mt-8 max-w-prose md:ml-12 md:mt-16">
				{#each skills as skill}
					<Heading tag="h3" size="sm" class="border-b-2 border-slate-400 pb-2 mb-2"
						>{skill.category}</Heading
					>
					<ul class="list-disc list-inside text-slate-600 space-y-2">
						{#each skill.items as item}
							<li
								class="mt-1 flex w-fit items-center gap-1 text-1xl font-semibold tracking-light text-slate-400"
							>
								{item}
							</li>
						{/each}
					</ul>
				{/each}
			</div>
		</div>
	</div>
</Bounded>
