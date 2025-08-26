<script lang="ts">
	// This component renders the main site header, featuring responsive navigation
	// for both desktop and mobile viewports.

	// Props
	// Adheres to the standard props pattern, though not utilized in this component's template.
	let { className = '' }: { className?: string } = $props();

	// State
	// Manages the visibility of the mobile navigation menu.
	let isMobileMenuOpen = $state(false);

	// Functions
	/**
	 * Toggles the open/closed state of the mobile menu.
	 */
	function toggleMobileMenu() {
		isMobileMenuOpen = !isMobileMenuOpen;
	}

	// Effects
	// Prevents body scrolling when the mobile menu is open for a better user experience.
	// The cleanup function restores the original scroll behavior when the menu is closed
	// or the component is unmounted.
	$effect(() => {
		if (isMobileMenuOpen) {
			const originalOverflow = document.body.style.overflow;
			document.body.style.overflow = 'hidden';
			return () => {
				document.body.style.overflow = originalOverflow;
			};
		}
	});
</script>

<header
	class="fixed top-0 z-50 w-full border-b border-gray-200 bg-[var(--color-background)] {className}"
>
	<div class="container flex h-24 items-center">
		<div class="relative flex h-full w-full items-center justify-between">
			<a href="/" aria-label="Home" class="font-display text-level-4xl text-gray-900"> Squint </a>

			<!-- Desktop Navigation -->
			<nav class="absolute left-1/2 hidden h-full -translate-x-1/2 items-center md:flex">
				<ul class="flex h-full items-center font-body text-level-lg font-medium">
					<li class="h-full">
						<button
							class="flex h-full items-center gap-x-1.5 px-4 text-gray-700 transition-colors hover:text-primary-600"
						>
							<span>Platform</span>
							<svg
								class="h-4 w-4 text-gray-500"
								xmlns="http://www.w3.org/2000/svg"
								fill="none"
								viewBox="0 0 24 24"
								stroke-width="2"
								stroke="currentColor"
								aria-hidden="true"
							>
								<path stroke-linecap="round" stroke-linejoin="round" d="m19.5 8.25-7.5 7.5-7.5-7.5" />
							</svg>
						</button>
					</li>
					<li class="h-full">
						<button
							class="flex h-full items-center gap-x-1.5 px-4 text-gray-700 transition-colors hover:text-primary-600"
						>
							<span>Solutions</span>
							<svg
								class="h-4 w-4 text-gray-500"
								xmlns="http://www.w3.org/2000/svg"
								fill="none"
								viewBox="0 0 24 24"
								stroke-width="2"
								stroke="currentColor"
								aria-hidden="true"
							>
								<path stroke-linecap="round" stroke-linejoin="round" d="m19.5 8.25-7.5 7.5-7.5-7.5" />
							</svg>
						</button>
					</li>
					<li class="h-full">
						<a
							href="/customers"
							class="flex h-full items-center px-4 text-gray-700 transition-colors hover:text-primary-600"
						>
							Customers
						</a>
					</li>
					<li class="h-full">
						<a
							href="/company"
							class="flex h-full items-center px-4 text-gray-700 transition-colors hover:text-primary-600"
						>
							Company
						</a>
					</li>
				</ul>
			</nav>

			<div class="flex h-full items-center">
				<!-- Desktop Action Buttons -->
				<div class="hidden h-full items-center gap-x-1 font-body md:flex">
					<a
						href="/login"
						class="flex h-full items-center px-7 text-level-lg font-medium text-gray-700 transition-colors hover:text-primary-600"
					>
						Login
					</a>
					<a
						href="/request-demo"
						class="flex h-8 items-center justify-center whitespace-nowrap rounded-sm bg-primary-600 px-3 text-level-lg font-medium text-white transition-colors hover:bg-primary-700"
					>
						Request a Demo
					</a>
				</div>

				<!-- Mobile Menu Toggle Button -->
				<button
					class="relative z-30 text-gray-700 md:hidden"
					type="button"
					aria-label={isMobileMenuOpen ? 'Close menu' : 'Open menu'}
					onclick={toggleMobileMenu}
					aria-expanded={isMobileMenuOpen}
					aria-controls="mobile-menu"
				>
					{#if isMobileMenuOpen}
						<!-- Close Icon -->
						<svg
							class="h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke-width="1.5"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path stroke-linecap="round" stroke-linejoin="round" d="M6 18L18 6M6 6l12 12" />
						</svg>
					{:else}
						<!-- Hamburger Icon -->
						<svg
							class="h-6 w-6"
							xmlns="http://www.w3.org/2000/svg"
							fill="none"
							viewBox="0 0 24 24"
							stroke-width="1.5"
							stroke="currentColor"
							aria-hidden="true"
						>
							<path
								stroke-linecap="round"
								stroke-linejoin="round"
								d="M3.75 6.75h16.5M3.75 12h16.5m-16.5 5.25h16.5"
							/>
						</svg>
					{/if}
				</button>
			</div>
		</div>
	</div>

	<!-- Mobile Navigation Panel -->
	{#if isMobileMenuOpen}
		<div id="mobile-menu" class="fixed inset-0 top-24 z-20 bg-white md:hidden">
			<nav
				class="flex h-full flex-col items-center space-y-8 pt-8 font-body text-level-2xl font-medium text-gray-700"
			>
				<button class="flex items-center gap-x-1.5 transition-colors hover:text-primary-600">
					<span>Platform</span>
					<svg
						class="h-4 w-4 text-gray-500"
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 24 24"
						stroke-width="2"
						stroke="currentColor"
						aria-hidden="true"
					>
						<path stroke-linecap="round" stroke-linejoin="round" d="m19.5 8.25-7.5 7.5-7.5-7.5" />
					</svg>
				</button>
				<button class="flex items-center gap-x-1.5 transition-colors hover:text-primary-600">
					<span>Solutions</span>
					<svg
						class="h-4 w-4 text-gray-500"
						xmlns="http://www.w3.org/2000/svg"
						fill="none"
						viewBox="0 0 24 24"
						stroke-width="2"
						stroke="currentColor"
						aria-hidden="true"
					>
						<path stroke-linecap="round" stroke-linejoin="round" d="m19.5 8.25-7.5 7.5-7.5-7.5" />
					</svg>
				</button>
				<a href="/customers" class="transition-colors hover:text-primary-600">Customers</a>
				<a href="/company" class="transition-colors hover:text-primary-600">Company</a>
				<div class="my-4 h-px w-full max-w-xs bg-gray-200" aria-hidden="true"></div>
				<a href="/login" class="transition-colors hover:text-primary-600">Login</a>
				<a
					href="/request-demo"
					class="flex h-10 items-center justify-center whitespace-nowrap rounded-sm bg-primary-600 px-4 text-level-xl text-white transition-colors hover:bg-primary-700"
				>
					Request a Demo
				</a>
			</nav>
		</div>
	{/if}
</header>