<script lang="ts">
	// Types
	type Logo = {
		src: string;
		alt: string;
	};

	// Props
	let { className = '' }: { className?: string } = $props();

	// State
	// This static array represents the logo data. In a real-world scenario,
	// this would be populated with actual client logos.
	const logos: Logo[] = Array(19).fill({
		src: 'https://www.ledr.com/colours/black.jpg', // Placeholder logo
		alt: 'Manufacturing client logo'
	});
</script>

<!--
  The component's theme and animations are defined inline to ensure it is self-contained.
  The background color is derived from the primary theme color for brand consistency.
-->
<style>
	@theme inline {
		--color-background: color-mix(in oklch, var(--color-primary-50) 55%, white);
	}

	@keyframes scroll {
		to {
			/* Moves the list by half its width plus one margin unit (1.5rem) to create a seamless loop. */
			transform: translate(calc(-50% - 1.5rem));
		}
	}

	.animate-logo-scroll {
		animation: scroll 60s linear infinite;
	}
</style>

<section id="customers" class="container overflow-hidden {className}">
	<div class="bg-[var(--color-background)] py-16 sm:py-24 lg:py-32">
		<div class="flex flex-col items-center gap-y-8">
			<h2 class="text-balance text-center text-level-4xl font-display font-medium text-gray-900">
				Trusted by Leading Manufacturers
			</h2>

			<div class="relative flex w-full flex-col items-center gap-y-6">
				<!-- Gradient fade for the left side of the scroller -->
				<div
					class="pointer-events-none absolute top-0 left-0 z-10 h-[78px] w-[20vw] bg-gradient-to-r from-[var(--color-background)] to-transparent md:w-[10vw]"
				></div>

				<!-- The scrolling container, clipped to create the marquee effect -->
				<div class="w-full max-w-[2000px] overflow-hidden">
					<ul class="flex w-max flex-nowrap animate-logo-scroll">
						<!-- The list is duplicated to create the seamless scrolling effect -->
						{#each logos as logo, i (i)}
							<li class="mx-6 h-[78px] w-fit flex-none">
								<img {...logo} loading="lazy" class="h-full w-auto" />
							</li>
						{/each}
						{#each logos as logo, i (`duplicate-${i}`)}
							<li class="mx-6 h-[78px] w-fit flex-none">
								<img {...logo} loading="lazy" class="h-full w-auto" />
							</li>
						{/each}
					</ul>
				</div>

				<!-- Gradient fade for the right side of the scroller -->
				<div
					class="pointer-events-none absolute top-0 right-0 z-10 h-[78px] w-[20vw] bg-gradient-to-l from-[var(--color-background)] to-transparent md:w-[10vw]"
				></div>

				<a
					href="#"
					class="text-level-lg flex items-center gap-x-1 font-body font-medium text-primary-600 transition-colors hover:text-primary-700"
				>
					<p>See Customers</p>
					<svg
						xmlns="http://www.w3.org/2000/svg"
						viewBox="0 0 20 20"
						fill="currentColor"
						class="h-5 w-5"
						aria-hidden="true"
					>
						<path
							fill-rule="evenodd"
							d="M2 10a.75.75 0 0 1 .75-.75h12.59l-2.1-1.95a.75.75 0 1 1 1.02-1.1l3.5 3.25a.75.75 0 0 1 0 1.1l-3.5 3.25a.75.75 0 1 1-1.02-1.1l2.1-1.95H2.75A.75.75 0 0 1 2 10Z"
							clip-rule="evenodd"
						></path>
					</svg>
				</a>
			</div>
		</div>
	</div>
</section>