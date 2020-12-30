<script>
    let message = '';
    const displayMessage = () => {
        message = `Thanks for reaching out! We've received your information and will get back to you shortly!`;
    };
</script>

<svelte:head>
    <title>Cumulus Creative Services - Contact</title>
</svelte:head>

<div class="relative bg-white mb-20">
    <div class="absolute inset-0">
        <div class="absolute inset-y-0 left-0 w-1/2 bg-white" />
    </div>
    <div class="relative max-w-screen-2xl mx-auto lg:grid lg:grid-cols-5">
        <div
            class="bg-primary py-16 px-4 sm:px-6 lg:col-span-2 lg:px-8 lg:py-24 xl:pr-12">
            <div class="max-w-lg mx-auto">
                <h2
                    class="text-2xl font-extrabold tracking-tight text-white sm:text-3xl">
                    Get in touch
                </h2>
                <p class="mt-3 text-lg leading-6 text-white">
                    Let us know how we can build the web and cloud solutions
                    your business needs.
                </p>
                <dl class="mt-8 text-base text-white">
                    <div class="mt-6">
                        <dt class="sr-only">Phone number</dt>
                        <dd class="flex">
                            <!-- Heroicon name: phone -->
                            <svg
                                class="flex-shrink-0 h-6 w-6 text-white"
                                xmlns="http://www.w3.org/2000/svg"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                                aria-hidden="true">
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
                            </svg>
                            <span class="ml-3"> +1 (330) 227-8316 </span>
                        </dd>
                    </div>
                    <div class="mt-3">
                        <dt class="sr-only">Email</dt>
                        <dd class="flex">
                            <!-- Heroicon name: mail -->
                            <svg
                                class="flex-shrink-0 h-6 w-6 text-white"
                                xmlns="http://www.w3.org/2000/svg"
                                fill="none"
                                viewBox="0 0 24 24"
                                stroke="currentColor"
                                aria-hidden="true">
                                <path
                                    stroke-linecap="round"
                                    stroke-linejoin="round"
                                    stroke-width="2"
                                    d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8M5 19h14a2 2 0 002-2V7a2 2 0 00-2-2H5a2 2 0 00-2 2v10a2 2 0 002 2z" />
                            </svg>
                            <span class="ml-3">
                                evan@cumulus-creative.com
                            </span>
                        </dd>
                    </div>
                </dl>
            </div>
        </div>
        <div
            class="bg-white py-16 px-4 sm:px-6 lg:col-span-3 lg:py-24 lg:px-8 xl:pl-12">
            <div class="max-w-lg mx-auto lg:max-w-none">
                <form
                    name="contact"
                    action="POST"
                    netlify
                    on:submit|preventDefault={displayMessage}
                    class="mt-9 grid grid-cols-1 gap-y-6 sm:grid-cols-2 sm:gap-x-8">
                    <div>
                        <label
                            for="first_name"
                            class="block text-sm font-medium text-gray-700">First
                            Name</label>
                        <div class="mt-1">
                            <input
                                type="text"
                                name="first_name"
                                id="first_name"
                                autocomplete="given-name"
                                class="block w-full shadow-sm sm:text-sm focus:ring-primary focus:border-primary border-gray-300 rounded-md" />
                        </div>
                    </div>
                    <div>
                        <label
                            for="last_name"
                            class="block text-sm font-medium text-gray-700">Last
                            Name</label>
                        <div class="mt-1">
                            <input
                                type="text"
                                name="last_name"
                                id="last_name"
                                autocomplete="family-name"
                                class="block w-full shadow-sm sm:text-sm focus:ring-primary focus:border-primary border-gray-300 rounded-md" />
                        </div>
                    </div>
                    <div class="sm:col-span-2">
                        <label
                            for="email"
                            class="block text-sm font-medium text-gray-700">Email</label>
                        <div class="mt-1">
                            <input
                                id="email"
                                name="email"
                                type="email"
                                autocomplete="email"
                                class="block w-full shadow-sm sm:text-sm focus:ring-primary focus:border-primary border-gray-300 rounded-md" />
                        </div>
                    </div>
                    <div class="sm:col-span-2">
                        <label
                            for="company"
                            class="block text-sm font-medium text-gray-700">Company</label>
                        <div class="mt-1">
                            <input
                                type="text"
                                name="company"
                                id="company"
                                autocomplete="organization"
                                class="block w-full shadow-sm sm:text-sm focus:ring-primary focus:border-primary border-gray-300 rounded-md" />
                        </div>
                    </div>
                    <div class="sm:col-span-2">
                        <div class="flex justify-between">
                            <label
                                for="phone"
                                class="block text-sm font-medium text-gray-700">Phone</label>
                            <span
                                id="phone_description"
                                class="text-sm text-gray-500">Optional</span>
                        </div>
                        <div class="mt-1">
                            <input
                                type="text"
                                name="phone"
                                id="phone"
                                autocomplete="tel"
                                aria-describedby="phone_description"
                                class="block w-full shadow-sm sm:text-sm focus:ring-primary focus:border-primary border-gray-300 rounded-md" />
                        </div>
                    </div>

                    <fieldset class="col-span-1">
                        <legend class="block text-sm font-medium text-gray-700">
                            Services Required
                        </legend>
                        <div class="mt-4 grid grid-cols-1 gap-y-4">
                            <div class="flex items-center">
                                <input
                                    id="website_dev"
                                    name="website-dev"
                                    value="website development"
                                    type="radio"
                                    class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                <label for="website_dev" class="ml-3">
                                    <span
                                        class="block text-sm text-gray-700">Website
                                        Development</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <input
                                    id="web_app_dev"
                                    name="web-app-dev"
                                    value="web app development"
                                    type="radio"
                                    class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                <label for="web_app_dev" class="ml-3">
                                    <span
                                        class="block text-sm text-gray-700">Web
                                        App Development</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <input
                                    id="mobile_app_dev"
                                    name="mobile-app-dev"
                                    value="mobile app development"
                                    type="radio"
                                    class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                <label for="mobile_app_dev" class="ml-3">
                                    <span
                                        class="block text-sm text-gray-700">Mobile
                                        App Development</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <input
                                    id="tech_consulting"
                                    name="tech-consulting"
                                    value="technology consulting"
                                    type="radio"
                                    class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                <label for="tech_consulting" class="ml-3">
                                    <span
                                        class="block text-sm text-gray-700">Technology
                                        Consulting</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <input
                                    id="automation"
                                    name="automation"
                                    value="automation"
                                    type="radio"
                                    class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                <label for="automation" class="ml-3">
                                    <span
                                        class="block text-sm text-gray-700">Automation</span>
                                </label>
                            </div>
                        </div>
                    </fieldset>
                    <fieldset class="col-span-1 mb-4">
                        <legend class="block text-sm font-medium text-gray-700">
                            Expected budget
                        </legend>
                        <div class="mt-4 grid grid-cols-1 gap-y-4">
                            <div class="flex items-center">
                                <input
                                    id="budget_under_5k"
                                    name="budget"
                                    value="under 5k"
                                    type="radio"
                                    class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                <label for="budget_under_5k" class="ml-3">
                                    <span
                                        class="block text-sm text-gray-700">Less
                                        than $5K</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <input
                                    id="budget_5k-15k"
                                    name="budget"
                                    value="5k-15k"
                                    type="radio"
                                    class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                <label for="budget_25k-50k" class="ml-3">
                                    <span
                                        class="block text-sm text-gray-700">$5K
                                        – $15K</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <input
                                    id="budget_15k-30k"
                                    name="budget"
                                    value="15k-30k"
                                    type="radio"
                                    class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                <label for="budget_15k-30k" class="ml-3">
                                    <span
                                        class="block text-sm text-gray-700">$15K
                                        – $30K</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <input
                                    id="budget_30k-50k"
                                    name="budget"
                                    value="30k-50k"
                                    type="radio"
                                    class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                <label for="budget_30k-50k" class="ml-3">
                                    <span
                                        class="block text-sm text-gray-700">$30K
                                        - $50k</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <input
                                    id="budget_over_50k"
                                    name="budget"
                                    value="over_50k"
                                    type="radio"
                                    class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                <label for="budget_over_50k" class="ml-3">
                                    <span
                                        class="block text-sm text-gray-700">$50K+</span>
                                </label>
                            </div>
                        </div>
                    </fieldset>
                    <div class="sm:col-span-2">
                        <div class="flex justify-between">
                            <label
                                for="how_can_we_help"
                                class="block text-sm font-medium text-gray-700">Tell
                                us a bit about your project, requirements, and
                                anything else that might be helpful.</label>
                        </div>
                        <div class="mt-1">
                            <textarea
                                id="how_can_we_help"
                                name="how_can_we_help"
                                aria-describedby="how_can_we_help_description"
                                rows="4"
                                class="block w-full shadow-sm sm:text-sm focus:ring-primary focus:border-primary border-gray-300 rounded-md" />
                        </div>
                    </div>
                    <div class="sm:col-span-2">
                        <label
                            for="how_did_you_hear_about_us"
                            class="block text-sm font-medium text-gray-700">How
                            did you hear about us?</label>
                        <div class="mt-1">
                            <input
                                type="text"
                                name="how_did_you_hear_about_us"
                                id="how_did_you_hear_about_us"
                                class="shadow-sm focus:ring-primary focus:border-primary block w-full sm:text-sm border-gray-300 rounded-md" />
                        </div>
                    </div>
                    <div class="text-right sm:col-span-2">
                        <button
                            type="submit"
                            class="inline-flex justify-center py-2 px-4 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-primary hover:bg-secondary focus:outline-none">
                            Submit
                        </button>
                    </div>
                    <div class="text-center sm:col-span-2">
                        <p>{message}</p>
                    </div>
                </form>
            </div>
        </div>
    </div>
</div>
