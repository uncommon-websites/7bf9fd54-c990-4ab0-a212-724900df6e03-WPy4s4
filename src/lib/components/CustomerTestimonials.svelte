<script lang="ts">
	// Types
	interface Testimonial {
		quote: string;
		name: string;
		title: string;
		company: string;
		logo: {
			alt: string;
			src: string;
			className: string;
		};
		backgroundSrc: string;
	}

	// Props
	let { className = '' }: { className?: string } = $props();

	// State
	const testimonials: Testimonial[] = $state.raw([
		{
			quote:
				'“Squint has been a game-changer for our production line. We’ve cut our new hire training time by 60% and reduced assembly errors by over 40%. Our tribal knowledge is finally captured and accessible.”',
			name: 'John Miller',
			title: 'Operations Manager',
			company: 'Apex Manufacturing',
			logo: {
				alt: 'Apex Manufacturing Logo',
				src: 'https://www.ledr.com/colours/white.jpg',
				className: 'h-20 w-auto md:h-28'
			},
			backgroundSrc: 'https://www.ledr.com/colours/white.jpg'
		},
		{
			quote:
				'“Before Squint, documenting a new process took days. Now, it happens automatically in minutes while our team works. It\'s completely removed the resistance to documentation and standardized our workflows.”',
			name: 'Maria Garcia',
			title: 'Director of Operations',
			company: 'Sterling Components',
			logo: {
				alt: 'Sterling Components Logo',
				src: 'https://www.ledr.com/colours/white.jpg',
				className: 'h-16 w-auto md:h-20'
			},
			backgroundSrc: 'https://www.ledr.com/colours/white.jpg'
		},
		{
			quote:
				'“I have been at the forefront of manufacturing tech for over 15 years, but I have never seen anything like Squint. It is a game-changer that can unleash the power of visual documentation to transform the factory floor.”',
			name: 'Sarah Chen',
			title: 'Head of Innovation',
			company: 'Dynamic Robotics',
			logo: {
				alt: 'Dynamic Robotics Logo',
				src: 'https://www.ledr.com/colours/white.jpg',
				className: 'h-16 w-auto md:h-20'
			},
			backgroundSrc: 'https://www.ledr.com/colours/white.jpg'
		},
		{
			quote:
				'“The implementation of Squint positions our team at the forefront of digital transformation in manufacturing. It\'s a significant achievement for our operations.”',
			name: 'Kenji Tanaka',
			title: 'Plant Manager',
			company: 'Precision Parts Inc.',
			logo: {
				alt: 'Precision Parts Inc. Logo',
				src: 'https://www.ledr.com/colours/white.jpg',
				className: 'h-16 w-auto md:h-20'
			},
			backgroundSrc: 'https://www.ledr.com/colours/white.jpg'
		},
		{
			quote:
				'“With Squint, you gain the ability to scale expertise rapidly and almost limitlessly. Our best practices are now everyone\'s practices.”',
			name: 'Emily Davis',
			title: 'Continuous Improvement Lead',
			company: 'Global Auto',
			logo: {
				alt: 'Global Auto Logo',
				src: 'https://www.ledr.com/colours/white.jpg',
				className: 'h-16 w-auto md:h-20'
			},
			backgroundSrc: 'https://www.ledr.com/colours/white.jpg'
		}
	]);

	let activeIndex = $state(0);
	let scrollContainer: HTMLDivElement | undefined = $state();
	let slideElements: HTMLElement[] = [];

	// Functions
	function handleDotClick(index: number) {
		slideElements[index]?.scrollIntoView({
			behavior: 'smooth',
			block: 'nearest',
			inline: 'start'
		});
	}

	// Effects
	$effect(() => {
		const container = scrollContainer;
		if (!container || slideElements.length === 0) return;

		const observer = new IntersectionObserver(
			(entries) => {
				for (const entry of entries) {
					if (entry.isIntersecting && entry.intersectionRatio >= 0.7) {
						const index = slideElements.findIndex((el) => el === entry.target);
						if (index !== -1) {
							activeIndex = index;
						}
					}
				}
			},
			{
				root: container,
				threshold: 0.7
			}
		);

		slideElements.forEach((el) => observer.observe(el));

		return () => {
			slideElements.forEach((el) => observer.unobserve(el));
		};
	});
</script>

<style>
	@theme inline {
		--color-background: color-mix(in oklch, var(--color-primary-50) 55%, white);
	}

	.scrollbar-hide::-webkit-scrollbar {
		display: none;
	}
	.scrollbar-hide {
		-ms-overflow-style: none;
		scrollbar-width: none;
	}
</style>

<section class="bg-[var(--color-background)] py-16 sm:py-24 lg:py-32 {className}">
	<div class="mx-auto max-w-[1728px] px-4 sm:px-6 lg:px-8">
		<div role="region" aria-roledescription="carousel" aria-label="Customer Testimonials">
			<div
				bind:this={scrollContainer}
				class="flex snap-x snap-mandatory overflow-x-auto pb-6 scrollbar-hide"
			>
				{#each testimonials as testimonial, i (testimonial.name)}
					<article
						bind:this={slideElements[i]}
						class="w-full flex-shrink-0 snap-start md:w-[70%] md:pr-12"
						aria-roledescription="slide"
						aria-label="{i + 1} of {testimonials.length}"
					>
						<a href="#" class="group block">
							<div class="relative overflow-hidden rounded-lg border border-gray-200">
								<img
									src={testimonial.backgroundSrc}
									alt="Abstract background for {testimonial.company} testimonial"
									loading="lazy"
									class="aspect-[5/4] w-full object-cover transition-transform duration-500 group-hover:scale-105 md:aspect-video"
								/>
								<div class="absolute inset-0 flex items-center justify-center bg-black/10 p-8">
									<img
										src={testimonial.logo.src}
										alt={testimonial.logo.alt}
										class={testimonial.logo.className}
									/>
								</div>
							</div>
							<div class="pt-8 md:flex md:items-start md:gap-8 md:px-6">
								<div class="flex-1">
									<blockquote class="font-body text-level-2xl text-gray-700">
										<p>{testimonial.quote}</p>
									</blockquote>
									<figcaption class="font-body mt-6 text-level-xl text-gray-600">
										<span class="font-medium text-gray-900">{testimonial.name}</span>,
										{testimonial.title}, {testimonial.company}
									</figcaption>
								</div>
								<div class="mt-6 flex-shrink-0 md:mt-0">
									<span
										class="font-body inline-flex items-center justify-center rounded-md bg-primary-600 px-5 py-3 text-level-xl font-medium text-white transition-colors hover:bg-primary-700"
									>
										Read Case Study
									</span>
								</div>
							</div>
						</a>
					</article>
				{/each}
			</div>

			<div class="mt-8 flex justify-center gap-3" role="group" aria-label="Slide controls">
				{#each testimonials as _, i (i)}
					<button
						onclick={() => handleDotClick(i)}
						aria-label="Go to slide {i + 1}"
						class="p-1"
						aria-current={activeIndex === i ? 'true' : 'false'}
					>
						<span
							class="block h-2.5 w-2.5 rounded-full transition"
							class:bg-primary-600={activeIndex === i}
							class:bg-gray-300={activeIndex !== i}
							class:hover:bg-gray-400={activeIndex !== i}
						></span>
					</button>
				{/each}
			</div>
		</div>
	</div>
</section>