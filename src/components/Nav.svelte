<script>
    import { fade } from 'svelte/transition';
    export let segment;

    let mobileMenu = false;
    let servicesOpen = false;
</script>

<div class="relative">
    <div class="max-w-screen-2xl mx-auto px-4 sm:px-6">
        <div class="flex justify-between items-center py-6 md:space-x-10">
            <div class="flex justify-start lg:w-0 lg:flex-1 items-center">
                <a href="/" class="mr-2">
                    <span class="sr-only">Workflow</span>
                    <img
                        class="h-6 w-10 sm:h-10"
                        src="favicon.png"
                        alt="cumulus creative logo" />
                </a>
                <a
                    href="/"
                    name="home"
                    class="text-lg font-semibold"
                    on:click={() => (servicesOpen = false)}>Cumulus Creative</a>
            </div>

            <div class="-mr-2 -my-2 md:hidden">
                <button
                    type="button"
                    class="rounded-md p-2 inline-flex items-center justify-center text-gray-400 hover:text-gray-500 focus:outline-none">
                    <span class="sr-only">Open menu</span>
                    <!-- Heroicon name: menu -->
                    <svg
                        on:click={() => (mobileMenu = true)}
                        class="w-6 h-6"
                        fill="none"
                        stroke="currentColor"
                        viewBox="0 0 24 24"
                        xmlns="http://www.w3.org/2000/svg"><path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M4 6h16M4 12h16m-7 6h7" /></svg>
                </button>
            </div>
            <nav class="hidden md:flex space-x-10">
                <div class="relative">
                    <!-- Item active: "text-gray-900", Item inactive: "text-gray-500" -->
                    <button
                        on:click={() => (servicesOpen = !servicesOpen)}
                        type="button"
                        class="group rounded-md text-gray-500 inline-flex items-center text-base font-medium hover:text-gray-900 focus:outline-none">
                        <span>Services</span>
                        <!--
              Heroicon name: chevron-down
              Item active: "text-gray-600", Item inactive: "text-gray-400"
            -->
                        {#if servicesOpen === false}
                            <svg
                                class="ml-2 h-4 w-4 text-gray-400 group-hover:text-gray-500"
                                fill="none"
                                stroke="currentColor"
                                viewBox="0 0 24 24"
                                xmlns="http://www.w3.org/2000/svg"><path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M19 9l-7 7-7-7" />
                            </svg>
                        {:else}
                            <svg
                                class="ml-2 h-4 w-4 text-gray-400 group-hover:text-gray-500"
                                fill="none"
                                stroke="currentColor"
                                viewBox="0 0 24 24"
                                xmlns="http://www.w3.org/2000/svg">
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M5 15l7-7 7 7" />
                            </svg>
                        {/if}
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
                            w-screen max-w-md sm:px-0 -ml-0 -left-28
                            -translate-x-1/2">
                            <div
                                class="rounded-lg shadow-lg ring-1 ring-black ring-opacity-5 overflow-hidden">
                                <div
                                    class="relative grid gap-6 bg-white px-5 py-6 sm:gap-8 sm:p-8">
                                    <a
                                        href="websites"
                                        name="websites"
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
                                                d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9" />
                                        </svg>
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
                                        name="web apps"
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
                                                Web applications for internal
                                                tools or customer-facing SaaS
                                                products.
                                            </p>
                                        </div>
                                    </a>

                                    <a
                                        href="mobile-apps"
                                        name="mobile apps"
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
                                                d="M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z" />
                                        </svg>
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
                                        href="technology-consulting"
                                        name="technology consoluting apps"
                                        class:bg-gray-100={segment === 'technology-consulting'}
                                        on:click={() => (servicesOpen = false)}
                                        class="-m-3 p-3 flex items-start rounded-lg hover:bg-gray-50">
                                        <svg
                                            class="w-6 h-6 text-primary"
                                            fill="none"
                                            stroke="currentColor"
                                            viewBox="0 0 24 24"
                                            xmlns="http://www.w3.org/2000/svg"><path
                                                stroke-linecap="round"
                                                stroke-linejoin="round"
                                                stroke-width="2"
                                                d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                                        </svg>
                                        <div class="ml-4">
                                            <p
                                                class="text-base font-medium text-gray-900">
                                                Technology Consolting
                                            </p>
                                            <p
                                                class="mt-1 text-sm text-gray-500">
                                                Advising on the best technology
                                                solutions for your business.
                                            </p>
                                        </div>
                                    </a>

                                    <a
                                        href="automation"
                                        name="automation"
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
                                                d="M9 3v2m6-2v2M9 19v2m6-2v2M5 9H3m2 6H3m18-6h-2m2 6h-2M7 19h10a2 2 0 002-2V7a2 2 0 00-2-2H7a2 2 0 00-2 2v10a2 2 0 002 2zM9 9h6v6H9V9z" />
                                        </svg>
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

                <!-- <a
                    href="about"
                    class:text-gray-900={segment === 'about'}
                    on:click={(servicesOpen = false)}
                    class="text-base font-medium text-gray-500 hover:text-gray-900">
                    About
                </a> -->
                <a
                    href="contact"
                    name="contact"
                    class:text-gray-900={segment === 'contact'}
                    on:click={(servicesOpen = false)}
                    class="text-base font-medium text-gray-500 hover:text-gray-900">
                    Contact
                </a>

                <div class="relative hidden">
                    <button
                        type="button"
                        class:text-gray-900={segment === 'work'}
                        class="group bg-white rounded-md text-gray-500 inline-flex items-center text-base font-medium hover:text-gray-900 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500">
                        <span>Work</span>
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
    {#if mobileMenu === true}
        <div
            class="absolute top-0 inset-x-0 p-2 transition transform origin-top-right md:hidden z-10">
            <div
                class="rounded-lg shadow-lg ring-1 ring-black ring-opacity-5 bg-white divide-y-2 divide-gray-50">
                <div class="pt-5 pb-6 px-5">
                    <div class="flex items-center justify-between">
                        <div>
                            <svg
                                class="w-6 mr-2 text-secondary"
                                fill="none"
                                stroke="currentColor"
                                viewBox="0 0 24 24"
                                xmlns="http://www.w3.org/2000/svg"><path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M3 15a4 4 0 004 4h9a5 5 0 10-.1-9.999 5.002 5.002 0 10-9.78 2.096A4.001 4.001 0 003 15z" />
                            </svg>
                        </div>
                        <div class="-mr-2">
                            <button
                                type="button"
                                class="bg-white rounded-md inline-flex items-center justify-center text-gray-400 hover:text-gray-500 focus:outline-none ">
                                <span class="sr-only">Close menu</span>
                                <svg
                                    on:click={() => (mobileMenu = false)}
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
                                href="websites"
                                class:bg-gray-100={segment === 'websites'}
                                on:click={() => (mobileMenu = false)}
                                class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50">
                                <svg
                                    class="flex-shrink-0 h-6 w-6 text-primary"
                                    fill="none"
                                    stroke="currentColor"
                                    viewBox="0 0 24 24"
                                    xmlns="http://www.w3.org/2000/svg"><path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        stroke-width="2"
                                        d="M21 12a9 9 0 01-9 9m9-9a9 9 0 00-9-9m9 9H3m9 9a9 9 0 01-9-9m9 9c1.657 0 3-4.03 3-9s-1.343-9-3-9m0 18c-1.657 0-3-4.03-3-9s1.343-9 3-9m-9 9a9 9 0 019-9" />
                                </svg>
                                <span
                                    class="ml-3 text-base font-medium text-gray-900">
                                    Websites
                                </span>
                            </a>

                            <a
                                href="web-apps"
                                class:bg-gray-100={segment === 'web-apps'}
                                on:click={() => (mobileMenu = false)}
                                class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50">
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
                                <span
                                    class="ml-3 text-base font-medium text-gray-900">
                                    Web Apps
                                </span>
                            </a>

                            <a
                                href="mobile-apps"
                                class:bg-gray-100={segment === 'mobile-apps'}
                                on:click={() => (mobileMenu = false)}
                                class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50">
                                <svg
                                    class="flex-shrink-0 h-6 w-6 text-primary"
                                    fill="none"
                                    stroke="currentColor"
                                    viewBox="0 0 24 24"
                                    xmlns="http://www.w3.org/2000/svg"><path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        stroke-width="2"
                                        d="M12 18h.01M8 21h8a2 2 0 002-2V5a2 2 0 00-2-2H8a2 2 0 00-2 2v14a2 2 0 002 2z" />
                                </svg>
                                <span
                                    class="ml-3 text-base font-medium text-gray-900">
                                    Mobile Apps
                                </span>
                            </a>

                            <a
                                href="technology-consulting"
                                class:bg-gray-100={segment === 'technology-consulting'}
                                on:click={() => (mobileMenu = false)}
                                class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50">
                                <svg
                                    class="w-6 h-6 text-primary"
                                    fill="none"
                                    stroke="currentColor"
                                    viewBox="0 0 24 24"
                                    xmlns="http://www.w3.org/2000/svg"><path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        stroke-width="2"
                                        d="M9.75 17L9 20l-1 1h8l-1-1-.75-3M3 13h18M5 17h14a2 2 0 002-2V5a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                                </svg>
                                <span
                                    class="ml-3 text-base font-medium text-gray-900">
                                    Technology Consolting
                                </span>
                            </a>

                            <a
                                href="automation"
                                class:bg-gray-100={segment === 'automation'}
                                on:click={() => (mobileMenu = false)}
                                class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50">
                                <svg
                                    class="flex-shrink-0 h-6 w-6 text-primary"
                                    fill="none"
                                    stroke="currentColor"
                                    viewBox="0 0 24 24"
                                    xmlns="http://www.w3.org/2000/svg"><path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        stroke-width="2"
                                        d="M9 3v2m6-2v2M9 19v2m6-2v2M5 9H3m2 6H3m18-6h-2m2 6h-2M7 19h10a2 2 0 002-2V7a2 2 0 00-2-2H7a2 2 0 00-2 2v10a2 2 0 002 2zM9 9h6v6H9V9z" />
                                </svg>
                                <span
                                    class="ml-3 text-base font-medium text-gray-900">
                                    Automation
                                </span>
                            </a>
                            <!-- <a
                                href="about"
                                class:bg-gray-100={segment === 'about'}
                                on:click={() => (mobileMenu = false)}
                                class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50">
                                About
                            </a> -->
                            <a
                                href="contact"
                                class:bg-gray-100={segment === 'contact'}
                                on:click={() => (mobileMenu = false)}
                                class="-m-3 p-3 flex items-center rounded-md hover:bg-gray-50">
                                <svg
                                    class="w-6 h-6 text-primary"
                                    fill="none"
                                    stroke="currentColor"
                                    viewBox="0 0 24 24"
                                    xmlns="http://www.w3.org/2000/svg"><path
                                        stroke-linecap="round"
                                        stroke-linejoin="round"
                                        stroke-width="2"
                                        d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                                </svg>
                                <span
                                    class="ml-3 text-base font-medium text-gray-900">
                                    Contact
                                </span>
                            </a>
                        </nav>
                    </div>
                </div>
            </div>
        </div>
    {/if}
</div>
