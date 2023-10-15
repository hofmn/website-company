<script lang="ts">

	function scrollToSection(sectionId: string): void {
			const section = document.getElementById(sectionId);
			if (section) {
			section.scrollIntoView({ behavior: 'smooth' });
			}
	}

</script>

<section>
	<div class="">
		<div class="container flex flex-col items-center px-4 py-16 pb-24 mx-auto text-center lg:pb-56 md:py-32 md:px-10 lg:px-32">
			<h1 class="text-5xl font-bold sm:text-6xl xl:max-w-3xls">Provident blanditiis cum exercitationem</h1>
			<p class="mt-6 mb-8 text-lg sm:mb-12 xl:max-w-3xl">Cupiditate minima voluptate temporibus quia? Architecto beatae esse ab amet vero eaque explicabo!</p>
			<div class="flex flex-wrap justify-center space-x-4">
				<button type="button" class="btn variant-filled-primary" on:click={() => scrollToSection('contact')}>Contact us</button>
				<button type="button" class="btn variant-ringed-primary" on:click={() => scrollToSection('products')}>Learn more</button>
			</div>
		</div>
	</div>
	<img src="https://source.unsplash.com/random/480x320" alt="" class="w-5/6 mx-auto mb-12 -mt-20 rounded-lg shadow-md lg:-mt-40 dark:bg-gray-500">
</section>