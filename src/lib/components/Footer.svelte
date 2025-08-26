<script lang="ts">
	// Props
	let { className = '' }: { className?: string } = $props();

	// Derived State
	const currentYear = $derived(new Date().getFullYear());
</script>

<style>
	@theme inline {
		--color-background: color-mix(in oklch, var(--color-primary-50) 55%, white);
	}
</style>

<footer class="container bg-[var(--color-background)] {className}">
	<section class="pb-7 md:pb-8 lg:pb-9 xl:pb-10">
		<div
			class="flex flex-col items-start gap-7 border-b border-gray-200 py-12 md:flex-row md:items-end md:justify-between md:py-24"
		>
			<h3
				class="w-full max-w-2xl font-display text-balance text-left font-medium text-gray-900 text-level-5xl"
			>
				Stop Production Delays. Start Standardizing.
			</h3>
			<a
				href="#"
				class="flex h-12 shrink-0 items-center justify-center whitespace-nowrap rounded-sm bg-primary-600 px-5 font-body font-medium leading-none text-white transition-colors duration-300 hover:bg-primary-700 text-level-xl"
				>Request a Demo</a
			>
		</div>
	</section>
	<section>
		<div class="flex flex-col justify-between py-16 md:grid md:grid-cols-12 md:py-24">
			<div class="mb-16 md:col-span-3 md:mb-0">
				<a href="#" class="font-display text-gray-900 text-level-4xl">Squint</a>
			</div>
			<div
				class="grid w-full grid-cols-2 gap-x-4 gap-y-12 md:col-span-6 md:col-start-7 md:grid-cols-4 md:gap-x-8"
			>
				<div class="flex flex-col gap-4">
					<small class="font-body text-gray-500 text-level-base">Platform</small>
					<a
						href="#"
						class="group flex font-body text-pretty font-medium text-gray-700 transition-colors hover:text-primary-600 text-level-base"
						>How It Works<span
							class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
							>→</span
						></a
					>
					<a
						href="#"
						class="group flex font-body text-pretty font-medium text-gray-700 transition-colors hover:text-primary-600 text-level-base"
						>Features<span
							class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
							>→</span
						></a
					>
					<a
						href="#"
						class="group flex font-body text-pretty font-medium text-gray-700 transition-colors hover:text-primary-600 text-level-base"
						>Security<span
							class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
							>→</span
						></a
					>
				</div>
				<div class="flex flex-col gap-4">
					<small class="font-body text-gray-500 text-level-base">Solutions</small>
					<a
						href="#"
						class="group flex font-body text-pretty font-medium text-gray-700 transition-colors hover:text-primary-600 text-level-base"
						>Onboarding<span
							class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
							>→</span
						></a
					>
					<a
						href="#"
						class="group flex font-body text-pretty font-medium text-gray-700 transition-colors hover:text-primary-600 text-level-base"
						>Assembly<span
							class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
							>→</span
						></a
					>
					<a
						href="#"
						class="group flex font-body text-pretty font-medium text-gray-700 transition-colors hover:text-primary-600 text-level-base"
						>Quality Control<span
							class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
							>→</span
						></a
					>
					<a
						href="#"
						class="group flex font-body text-pretty font-medium text-gray-700 transition-colors hover:text-primary-600 text-level-base"
						>Standardization<span
							class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
							>→</span
						></a
					>
				</div>
				<div class="flex flex-col gap-4">
					<small class="font-body text-gray-500 text-level-base">About</small>
					<a
						href="#"
						class="group flex font-body text-pretty font-medium text-gray-700 transition-colors hover:text-primary-600 text-level-base"
						>Customers<span
							class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
							>→</span
						></a
					>
					<a
						href="#"
						class="group flex font-body text-pretty font-medium text-gray-700 transition-colors hover:text-primary-600 text-level-base"
						>Company<span
							class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
							>→</span
						></a
					>
					<a
						href="#"
						class="group flex font-body text-pretty font-medium text-gray-700 transition-colors hover:text-primary-600 text-level-base"
						>Blog<span class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
							>→</span
						></a
					>
					<a
						href="#"
						class="group flex font-body text-pretty font-medium text-gray-700 transition-colors hover:text-primary-600 text-level-base"
						>Careers<span
							class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
							>→</span
						></a
					>
				</div>
				<div class="flex flex-col gap-4">
					<small class="font-body text-gray-500 text-level-base">Resources</small>
					<a
						href="#"
						class="group flex font-body text-pretty font-medium text-gray-700 transition-colors hover:text-primary-600 text-level-base"
						>Contact Us<span
							class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
							>→</span
						></a
					>
					<a
						href="#"
						class="group flex font-body text-pretty font-medium text-gray-700 transition-colors hover:text-primary-600 text-level-base"
						>Privacy Policy<span
							class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
							>→</span
						></a
					>
					<a
						href="#"
						class="group flex font-body text-pretty font-medium text-gray-700 transition-colors hover:text-primary-600 text-level-base"
						>Terms of Service<span
							class="opacity-0 transition-all group-hover:ml-1 group-hover:opacity-100"
							>→</span
						></a
					>
				</div>
			</div>
		</div>
		<div
			class="flex flex-col-reverse gap-6 pb-7 md:flex-row md:items-center md:justify-between md:pb-8 lg:pb-9 xl:pb-10"
		>
			<p class="font-body text-balance text-gray-500 text-level-base">
				Copyright © {currentYear} Squint AI Corporation. All rights reserved.
			</p>
			<div class="flex items-center gap-4">
				<a
					href="#"
					target="_blank"
					class="font-body text-gray-500 transition-colors hover:text-primary-600 text-level-base"
					>X</a
				>
				<div class="h-3 w-px bg-gray-300"></div>
				<a
					href="#"
					target="_blank"
					class="font-body text-gray-500 transition-colors hover:text-primary-600 text-level-base"
					>LinkedIn</a
				>
			</div>
		</div>
	</section>
</footer>