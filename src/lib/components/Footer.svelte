<script lang="ts">
	import type { Content } from '@prismicio/client';

	export let settings: Content.SettingsDocument;
	console.log(settings);
</script>

<footer class="text-slate-600">
	<div class="container">
		<div class="name">
			<a
				href="/"
				class="text-xl font-extrabold tracking-tighter text-slate-100 transition-color duration-150 hover:text-yellow-400"
			>
				{settings.data.name}
			</a>
		</div>
		<div class="navigation">Profile</div>
		<div class="socials">Socials</div>
	</div>
</footer>
