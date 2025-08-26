<script lang="ts">
	// Types
	type Solution = {
		title: string;
		description: string;
		imageUrl: string;
		imageAlt: string;
		linkUrl: string;
		imageOnRight: boolean;
	};

	// Props
	let { className = '' }: { className?: string } = $props();

	// Static data for the solutions.
	// This approach keeps content within the component while making the template cleaner and more maintainable.
	const solutions: Solution[] = [
		{
			title: 'New Hire Onboarding',
			description:
				'Slash training time and get new hires up to speed faster with clear, standardized visual guides for every core process.',
			imageUrl: 'https://www.ledr.com/colours/white.jpg',
			imageAlt: 'Team members onboarding a new hire using Squint',
			linkUrl: '#',
			imageOnRight: true
		},
		{
			title: 'Complex Assembly',
			description:
				'Eliminate errors and ensure consistency by providing detailed, easy-to-follow instructions for your most intricate assembly tasks.',
			imageUrl: 'https://www.ledr.com/colours/white.jpg',
			imageAlt: 'Worker performing complex assembly with Squint instructions',
			linkUrl: '#',
			imageOnRight: false
		},
		{
			title: 'Quality Control',
			description:
				'Standardize quality checks and compliance procedures. Ensure every team member follows the exact same process, every time.',
			imageUrl: 'https://www.ledr.com/colours/white.jpg',
			imageAlt: 'Quality control check being performed',
			linkUrl: '#',
			imageOnRight: true
		},
		{
			title: 'Process Standardization',
			description:
				'Capture best practices from your top performers and turn scattered tribal knowledge into a reliable, centralized resource.',
			imageUrl: 'https://www.ledr.com/colours/white.jpg',
			imageAlt: 'Standard operating procedure document created by Squint',
			linkUrl: '#',
			imageOnRight: false
		}
	];
</script>

<section class="container bg-[var(--color-background)] {className}">
	<div class="mb-12 text-center md:mb-16">
		<span class="font-body text-level-2xl text-gray-600">
			Solutions for Your Biggest Operational Challenges
		</span>
		<h2 class="font-display text-level-5xl mt-2 text-balance font-medium text-gray-900">
			How Manufacturing Teams Use Squint
		</h2>
	</div>

	<div class="flex flex-col gap-8 md:gap-12 lg:gap-16">
		{#each solutions as solution}
			<article class="flex flex-col overflow-hidden rounded-lg border border-gray-200 bg-white md:flex-row">
				<div
					class="relative aspect-square w-full md:w-1/2"
					class:md:order-last={solution.imageOnRight}
				>
					<img
						class="h-full w-full object-cover"
						src={solution.imageUrl}
						alt={solution.imageAlt}
					/>
				</div>
				<div class="flex w-full items-center justify-center p-8 sm:p-12 md:w-1/2 md:p-16 lg:p-24">
					<div class="flex max-w-xs flex-col gap-4 md:gap-5">
						<h3 class="font-display text-level-4xl text-balance font-medium text-gray-900">
							{solution.title}
						</h3>
						<p class="font-body text-level-lg text-gray-600">
							{solution.description}
						</p>
						<a
							href={solution.linkUrl}
							class="group mt-2 inline-flex items-center gap-2 font-body text-level-lg font-medium text-primary-600 transition-colors hover:text-primary-700"
						>
							Learn More
							<span
								aria-hidden="true"
								class="transition-transform group-hover:translate-x-1"
							>
								→
							</span>
						</a>
					</div>
				</div>
			</article>
		{/each}
	</div>
</section>