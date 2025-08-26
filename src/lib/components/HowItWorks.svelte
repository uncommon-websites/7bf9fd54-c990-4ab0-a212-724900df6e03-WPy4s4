<script lang="ts">
	// Types
	type Step = {
		number: string;
		title: string;
		description: string;
	};

	// Props
	let { className = '' }: { className?: string } = $props();

	// Static data for the steps. This keeps content within the component
	// while making the template cleaner and more maintainable.
	const steps: Step[] = [
		{
			number: '01',
			title: 'Record Any Process',
			description:
				'Simply perform a task on-screen. Squint’s computer vision works in the background to capture every step without interrupting your workflow.'
		},
		{
			number: '02',
			title: 'AI Generates Instructions',
			description:
				'Our AI instantly converts the recording into a step-by-step visual guide, complete with screenshots, annotations, and clear descriptions.'
		},
		{
			number: '03',
			title: 'Access Anywhere, Instantly',
			description:
				'Your team gets immediate access to a searchable library of work instructions, available on any device, right when they need it.'
		}
	];
</script>

<section class="bg-[var(--color-background)] py-16 lg:py-32 {className}">
	<div class="container">
		<div class="flex flex-col items-center justify-center gap-12 lg:gap-16">
			<div
				class="relative flex w-full items-center justify-center overflow-hidden rounded-2xl bg-primary-100 px-6 py-20"
			>
				<img
					src="https://www.ledr.com/colours/black.jpg"
					alt="Abstract background pattern"
					class="absolute inset-0 h-full w-full object-cover opacity-5"
				/>
				<div class="relative z-10 flex flex-col items-center justify-center gap-8">
					<svg
						width="37"
						height="26"
						viewBox="0 0 37 26"
						xmlns="http://www.w3.org/2000/svg"
						class="h-[26px] w-[37px] text-primary-600"
						aria-hidden="true"
					>
						<path d="M18.5 0L12.3333 10.6667H24.6667L18.5 0Z" fill="currentColor" />
						<path d="M11.5625 11.8542L5.39583 22.5208H17.7292L11.5625 11.8542Z" fill="currentColor" />
						<path d="M25.4375 11.8542L19.2708 22.5208H31.6042L25.4375 11.8542Z" fill="currentColor" />
					</svg>
					<div class="flex flex-col items-center gap-6">
						<h2
							class="text-balance text-center font-display text-level-5xl font-normal tracking-tight text-gray-900"
						>
							Capture Knowledge in 3 Simple Steps
						</h2>
						<p
							class="max-w-md text-balance text-center font-body text-level-lg font-normal text-gray-700"
						>
							Squint makes process documentation effortless, turning your team's actions into a
							powerful knowledge base.
						</p>
					</div>
				</div>
			</div>

			<div class="flex w-full flex-col gap-3 lg:flex-row">
				{#each steps as step (step.number)}
					<div class="flex flex-1 flex-col gap-2 rounded-2xl border border-gray-200 bg-white p-5">
						<div class="flex items-center gap-2">
							<h3 class="font-display text-level-2xl font-normal text-primary-600">
								{step.number}
							</h3>
							<h3 class="font-display text-level-2xl font-normal text-gray-900">
								{step.title}
							</h3>
						</div>
						<p class="font-body text-level-lg font-normal text-gray-600">
							{step.description}
						</p>
					</div>
				{/each}
			</div>
		</div>
	</div>
</section>