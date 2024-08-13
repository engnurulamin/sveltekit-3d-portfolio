<script lang="ts">
	import Bounded from '$lib/components/Bounded.svelte';
	import Heading from '$lib/components/Heading.svelte';
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
		<!-- Left Column: Experience -->
		<div class="flex flex-col p-8 text-slate-400">
			<Heading tag="h2" size="md">{slice.primary.heading}</Heading>
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
		</div>

		<!-- Right Column: Technologies I Use -->
		<div class="flex flex-col p-8 text-slate-400">
			<Heading tag="h2" size="md">Technologies I Use</Heading>
			<p>
				Lorem ipsum dolor sit amet consectetur adipisicing elit. Excepturi numquam nulla, eos vero
				sequi ea quis, nihil quibusdam cum enim labore voluptatem rerum maxime velit perspiciatis,
				saepe aliquam ex blanditiis.
			</p>
		</div>
	</div>
</Bounded>
