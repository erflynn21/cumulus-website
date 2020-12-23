<script>
    import { fade } from 'svelte/transition';
    export let segment;

    let mobileMenu = false;
    let servicesOpen = false;
</script>

<div class="relative">
    <div class="max-w-screen-2xl mx-auto px-4 sm:px-6">
        <div class="flex justify-between items-center py-6 md:space-x-10">
            <div class="flex justify-start lg:w-0 lg:flex-1">
                <!-- <a href="#">
                    <span class="sr-only">Workflow</span>
                    <img
                        class="h-8 w-auto sm:h-10"
                        src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg"
                        alt="" />
				</a> -->
                <svg
                    class="w-6 mr-2 text-secondary"
                    fill="none"
                    stroke="currentColor"
                    viewBox="0 0 24 24"
                    xmlns="http://www.w3.org/2000/svg"><path
                        stroke-linecap="round"
                        stroke-linejoin="round"
                        stroke-width="2"
                        d="M3 15a4 4 0 004 4h9a5 5 0 10-.1-9.999 5.002 5.002 0 10-9.78 2.096A4.001 4.001 0 003 15z" /></svg>
                <a href="/" class="text-lg font-semibold">Cumulus Creative</a>
            </div>

            <div class="-mr-2 -my-2 md:hidden">
                <button
                    type="button"
                    class="bg-white rounded-md p-2 inline-flex items-center justify-center text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500">
                    <span class="sr-only">Open menu</span>
                    <!-- Heroicon name: menu -->
                    <svg
                        class="h-6 w-6"
                        xmlns="http://www.w3.org/2000/svg"
                        fill="none"
                        viewBox="0 0 24 24"
                        stroke="currentColor"
                        aria-hidden="true">
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M4 6h16M4 12h16M4 18h16" />
                    </svg>
                </button>
            </div>
            <nav class="hidden md:flex space-x-10">
                <div class="relative">
                    <!-- Item active: "text-gray-900", Item inactive: "text-gray-500" -->
                    <button
                        on:click={() => (servicesOpen = !servicesOpen)}
                        type="button"
                        class="group bg-white rounded-md text-gray-500 inline-flex items-center text-base font-medium hover:text-gray-900 focus:outline-none">
                        <span>Services</span>
                        <!--
              Heroicon name: chevron-down

              Item active: "text-gray-600", Item inactive: "text-gray-400"
            -->
                        <svg
                            class="ml-2 h-5 w-5 text-gray-400 group-hover:text-gray-500"
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 20 20"
                            fill="currentColor"
                            aria-hidden="true">
                            <path
                                fill-rule="evenodd"
                                d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                                clip-rule="evenodd" />
                        </svg>
                    </button>

                    <!--                     
            'Services' flyout menu, show/hide based on flyout menu state.

            Entering: "transition ease-out duration-200"
              From: "opacity-0 translate-y-1"
              To: "opacity-100 translate-y-0"
            Leaving: "transition ease-in duration-150"
              From: "opacity-100 translate-y-0"
              To: "opacity-0 translate-y-1"
		  -->
                    {#if servicesOpen === true}
                        <div
                            in:fade={{ duration: 200 }}
                            out:fade={{ duration: 150 }}
                            class="absolute z-10 mt-3 transform px-2
                            w-screen max-w-md sm:px-0 -ml-0 left-1/2
                            -translate-x-1/2">
                            <div
                                class="rounded-lg shadow-lg ring-1 ring-black ring-opacity-5 overflow-hidden">
                                <div
                                    class="relative grid gap-6 bg-white px-5 py-6 sm:gap-8 sm:p-8">
                                    <a
                                        href="websites"
                                        class:bg-gray-100={segment === 'websites'}
                                        on:click={() => (servicesOpen = false)}
                                        class="-m-3 p-3 flex items-start rounded-lg hover:bg-gray-50">
                                        <!-- Heroicon name: chart-bar -->
                                        <svg
                                            class="flex-shrink-0 h-6 w-6 text-primary"
                                            fill="none"
                                            stroke="currentColor"
                                            viewBox="0 0 24 24"
                                            xmlns="http://www.w3.org/2000/svg"><path
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9" /></svg>
                                        <div class="ml-4">
                                            <p
                                                class="text-base font-medium text-gray-900">
                                                Websites
                                            </p>
                                            <p
                                                class="mt-1 text-sm text-gray-500">
                                                Websites designed and built
                                                around your business needs.
                                            </p>
                                        </div>
                                    </a>

                                    <a
                                        href="web-apps"
                                        class:bg-gray-100={segment === 'web-apps'}
                                        on:click={() => (servicesOpen = false)}
                                        class="-m-3 p-3 flex items-start rounded-lg hover:bg-gray-50">
                                        <svg
                                            class="flex-shrink-0 h-6 w-6 text-primary"
                                            xmlns="http://www.w3.org/2000/svg"
                                            fill="none"
                                            viewBox="0 0 24 24"
                                            stroke="currentColor"
                                            aria-hidden="true">
                                            <path
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                d="M15 15l-2 5L9 9l11 4-5 2zm0 0l5 5M7.188 2.239l.777 2.897M5.136 7.965l-2.898-.777M13.95 4.05l-2.122 2.122m-5.657 5.656l-2.12 2.122" />
                                        </svg>
                                        <div class="ml-4">
                                            <p
                                                class="text-base font-medium text-gray-900">
                                                Web Apps
                                            </p>
                                            <p
                                                class="mt-1 text-sm text-gray-500">
                                                Web applications allow for
                                                interactivacity and user
                                                accounts.
                                            </p>
                                        </div>
                                    </a>

                                    <a
                                        href="mobile-apps"
                                        class:bg-gray-100={segment === 'mobile-apps'}
                                        on:click={() => (servicesOpen = false)}
                                        class="-m-3 p-3 flex items-start rounded-lg hover:bg-gray-50">
                                        <svg
                                            class="flex-shrink-0 h-6 w-6 text-primary"
                                            fill="none"
                                            stroke="currentColor"
                                            viewBox="0 0 24 24"
                                            xmlns="http://www.w3.org/2000/svg"><path
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                d="M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z" /></svg>
                                        <div class="ml-4">
                                            <p
                                                class="text-base font-medium text-gray-900">
                                                Mobile Apps
                                            </p>
                                            <p
                                                class="mt-1 text-sm text-gray-500">
                                                Apps designed to run on iOS and
                                                Android mobile phones.
                                            </p>
                                        </div>
                                    </a>

                                    <a
                                        href="automation"
                                        class:bg-gray-100={segment === 'automation'}
                                        on:click={() => (servicesOpen = false)}
                                        class="-m-3 p-3 flex items-start rounded-lg hover:bg-gray-50">
                                        <svg
                                            class="flex-shrink-0 h-6 w-6 text-primary"
                                            fill="none"
                                            stroke="currentColor"
                                            viewBox="0 0 24 24"
                                            xmlns="http://www.w3.org/2000/svg"><path
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                d="M9 3v2m6-2v2M9 19v2m6-2v2M5 9H3m2 6H3m18-6h-2m2 6h-2M7 19h10a2 2 0 002-2V7a2 2 0 00-2-2H7a2 2 0 00-2 2v10a2 2 0 002 2zM9 9h6v6H9V9z" /></svg>
                                        <div class="ml-4">
                                            <p
                                                class="text-base font-medium text-gray-900">
                                                Automation
                                            </p>
                                            <p
                                                class="mt-1 text-sm text-gray-500">
                                                Strategically automate tasks
                                                across your business to save
                                                time and money.
                                            </p>
                                        </div>
                                    </a>
                                </div>
                            </div>
                        </div>
                    {/if}
                </div>

                <a
                    href="about"
                    class:text-gray-900={segment === 'about'}
                    on:click={(servicesOpen = false)}
                    class="text-base font-medium text-gray-500 hover:text-gray-900">
                    About
                </a>
                <a
                    href="contact"
                    class:text-gray-900={segment === 'contact'}
                    on:click={(servicesOpen = false)}
                    class="text-base font-medium text-gray-500 hover:text-gray-900">
                    Contact
                </a>

                <div class="relative hidden">
                    <!-- Item active: "text-gray-900", Item inactive: "text-gray-500" -->
                    <button
                        type="button"
                        class:text-gray-900={segment === 'work'}
                        class="group bg-white rounded-md text-gray-500 inline-flex items-center text-base font-medium hover:text-gray-900 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
                        <span>Work</span>
                        <!--
              Heroicon name: chevron-down

              Item active: "text-gray-600", Item inactive: "text-gray-400"
            -->
                        <svg
                            class="ml-2 h-5 w-5 text-gray-400 group-hover:text-gray-500"
                            xmlns="http://www.w3.org/2000/svg"
                            viewBox="0 0 20 20"
                            fill="currentColor"
                            aria-hidden="true">
                            <path
                                fill-rule="evenodd"
                                d="M5.293 7.293a1 1 0 011.414 0L10 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z"
                                clip-rule="evenodd" />
                        </svg>
                    </button>
                </div>
            </nav>
        </div>
    </div>

    <!--
    Mobile menu, show/hide based on mobile menu state.

    Entering: "duration-200 ease-out"
      From: "opacity-0 scale-95"
      To: "opacity-100 scale-100"
    Leaving: "duration-100 ease-in"
      From: "opacity-100 scale-100"
      To: "opacity-0 scale-95"
  -->
    <div
        class="absolute top-0 inset-x-0 p-2 transition transform origin-top-right md:hidden">
        <div
            class="rounded-lg shadow-lg ring-1 ring-black ring-opacity-5 bg-white divide-y-2 divide-gray-50">
            <div class="pt-5 pb-6 px-5">
                <div class="flex items-center justify-between">
                    <div>
                        <img
                            class="h-8 w-auto"
                            src="https://tailwindui.com/img/logos/workflow-mark-indigo-600.svg"
                            alt="Workflow" />
                    </div>
                    <div class="-mr-2">
                        <button
                            type="button"
                            class="bg-white rounded-md p-2 inline-flex items-center justify-center text-gray-400 hover:text-gray-500 hover:bg-gray-100 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-indigo-500">
                            <span class="sr-only">Close menu</span>
                            <!-- Heroicon name: x -->
                            <svg
                                class="h-6 w-6"
                                xmlns="http://www.w3.org/2000/svg"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                                aria-hidden="true">
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M6 18L18 6M6 6l12 12" />
                            </svg>
                        </button>
                    </div>
                </div>
                <div class="mt-6">
                    <nav class="grid gap-y-8">
                        <a
                            href="#"
                            class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50">
                            <!-- Heroicon name: chart-bar -->
                            <svg
                                class="flex-shrink-0 h-6 w-6 text-indigo-600"
                                xmlns="http://www.w3.org/2000/svg"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                                aria-hidden="true">
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M9 19v-6a2 2 0 00-2-2H5a2 2 0 00-2 2v6a2 2 0 002 2h2a2 2 0 002-2zm0 0V9a2 2 0 012-2h2a2 2 0 012 2v10m-6 0a2 2 0 002 2h2a2 2 0 002-2m0 0V5a2 2 0 012-2h2a2 2 0 012 2v14a2 2 0 01-2 2h-2a2 2 0 01-2-2z" />
                            </svg>
                            <span
                                class="ml-3 text-base font-medium text-gray-900">
                                Analytics
                            </span>
                        </a>

                        <a
                            href="#"
                            class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50">
                            <!-- Heroicon name: cursor-click -->
                            <svg
                                class="flex-shrink-0 h-6 w-6 text-indigo-600"
                                xmlns="http://www.w3.org/2000/svg"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                                aria-hidden="true">
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M15 15l-2 5L9 9l11 4-5 2zm0 0l5 5M7.188 2.239l.777 2.897M5.136 7.965l-2.898-.777M13.95 4.05l-2.122 2.122m-5.657 5.656l-2.12 2.122" />
                            </svg>
                            <span
                                class="ml-3 text-base font-medium text-gray-900">
                                Engagement
                            </span>
                        </a>

                        <a
                            href="#"
                            class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50">
                            <!-- Heroicon name: shield-check -->
                            <svg
                                class="flex-shrink-0 h-6 w-6 text-indigo-600"
                                xmlns="http://www.w3.org/2000/svg"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                                aria-hidden="true">
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M9 12l2 2 4-4m5.618-4.016A11.955 11.955 0 0112 2.944a11.955 11.955 0 01-8.618 3.04A12.02 12.02 0 003 9c0 5.591 3.824 10.29 9 11.622 5.176-1.332 9-6.03 9-11.622 0-1.042-.133-2.052-.382-3.016z" />
                            </svg>
                            <span
                                class="ml-3 text-base font-medium text-gray-900">
                                Security
                            </span>
                        </a>

                        <a
                            href="#"
                            class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50">
                            <!-- Heroicon name: view-grid -->
                            <svg
                                class="flex-shrink-0 h-6 w-6 text-indigo-600"
                                xmlns="http://www.w3.org/2000/svg"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                                aria-hidden="true">
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M4 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2V6zM14 6a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2V6zM4 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2H6a2 2 0 01-2-2v-2zM14 16a2 2 0 012-2h2a2 2 0 012 2v2a2 2 0 01-2 2h-2a2 2 0 01-2-2v-2z" />
                            </svg>
                            <span
                                class="ml-3 text-base font-medium text-gray-900">
                                Integrations
                            </span>
                        </a>

                        <a
                            href="#"
                            class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50">
                            <!-- Heroicon name: refresh -->
                            <svg
                                class="flex-shrink-0 h-6 w-6 text-indigo-600"
                                xmlns="http://www.w3.org/2000/svg"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                                aria-hidden="true">
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M4 4v5h.582m15.356 2A8.001 8.001 0 004.582 9m0 0H9m11 11v-5h-.581m0 0a8.003 8.003 0 01-15.357-2m15.357 2H15" />
                            </svg>
                            <span
                                class="ml-3 text-base font-medium text-gray-900">
                                Automations
                            </span>
                        </a>
                    </nav>
                </div>
            </div>
            <div class="py-6 px-5 space-y-6">
                <div class="grid grid-cols-2 gap-y-4 gap-x-8">
                    <a
                        href="#"
                        class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Pricing
                    </a>

                    <a
                        href="#"
                        class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Docs
                    </a>

                    <a
                        href="#"
                        class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Enterprise
                    </a>

                    <a
                        href="#"
                        class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Blog
                    </a>

                    <a
                        href="#"
                        class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Help Center
                    </a>

                    <a
                        href="#"
                        class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Guides
                    </a>

                    <a
                        href="#"
                        class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Security
                    </a>

                    <a
                        href="#"
                        class="text-base font-medium text-gray-900 hover:text-gray-700">
                        Events
                    </a>
                </div>
                <div>
                    <a
                        href="#"
                        class="w-full flex items-center justify-center px-4 py-2 border border-transparent rounded-md shadow-sm text-base font-medium text-white bg-indigo-600 hover:bg-indigo-700">
                        Sign up
                    </a>
                    <p
                        class="mt-6 text-center text-base font-medium text-gray-500">
                        Existing customer?
                        <a
                            href="#"
                            class="text-indigo-600 hover:text-indigo-500">
                            Sign in
                        </a>
                    </p>
                </div>
            </div>
        </div>
    </div>
</div>

<style>
</style>
