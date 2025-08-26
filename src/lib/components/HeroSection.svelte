<script lang="ts">
	// Props
	let { className = '' }: { className?: string } = $props();

	// Functions
	/**
	 * Handles the click event for the play video button.
	 * In a real application, this would typically open a video modal or player.
	 */
	function handlePlayClick(): void {
		console.log('Play video action triggered.');
		// Logic to open a video player/modal would go here.
	}
</script>

<section class="container {className}">
	<div class="bg-[var(--color-background)] pt-24 pb-16 sm:pb-24 lg:pb-32">
		<div class="flex flex-col items-center gap-8">
			<div class="flex flex-col items-center gap-4 text-center">
				<h1 class="text-balance font-display text-level-5xl text-gray-900">
					Turn Expertise into<br />
					Instructions. Instantly.
				</h1>
				<p class="mx-auto max-w-xl text-balance font-body font-normal text-level-xl text-gray-700">
					Squint uses computer vision to automatically transform complex processes into simple,
					visual instructions for your manufacturing team.
				</p>
			</div>
			<a
				href="#"
				class="flex h-12 cursor-pointer items-center justify-center whitespace-nowrap rounded-sm bg-primary-600 px-5 font-body font-medium text-level-lg text-white transition-colors duration-300 hover:bg-primary-700 focus:outline-none focus:ring-2 focus:ring-primary-500 focus:ring-offset-2 focus:ring-offset-[var(--color-background)] active:bg-primary-800"
			>
				Request a Demo
			</a>
			<div class="mt-8 w-full md:mt-16">
				<div
					class="group relative aspect-video w-full cursor-pointer overflow-hidden rounded-sm border border-gray-200"
				>
					<div class="absolute inset-0 bg-gray-100">
						<img
							alt="Demonstration of Squint's process capture technology"
							src="https://www.ledr.com/colours/white.jpg"
							class="h-full w-full object-cover"
						/>
					</div>
					<button
						onclick={handlePlayClick}
						aria-label="Play Video"
						class="absolute left-1/2 top-1/2 z-10 -translate-x-1/2 -translate-y-1/2 scale-75 backdrop-blur-sm transition-opacity duration-500 md:scale-100"
					>
						<div
							class="flex h-14 w-14 items-center overflow-hidden rounded-sm bg-white/50 transition-all duration-500 ease-in-out group-hover:w-44 group-hover:bg-white/70 md:h-[72px] md:w-[72px]"
						>
							<div
								class="flex items-center gap-2 pl-4 transition-transform duration-500 ease-in-out md:pl-5"
							>
								<svg
									class="h-6 w-6 flex-shrink-0 text-gray-900"
									fill="currentColor"
									viewBox="0 0 24 24"
									aria-hidden="true"
								>
									<path d="M7.5 5.25L17.25 12L7.5 18.75V5.25Z" />
								</svg>
								<span
									class="whitespace-nowrap font-body text-level-lg text-gray-900 opacity-0 transition-opacity duration-300 group-hover:opacity-100"
								>
									Watch Video
								</span>
							</div>
						</div>
					</button>
				</div>
			</div>
		</div>
	</div>
</section>