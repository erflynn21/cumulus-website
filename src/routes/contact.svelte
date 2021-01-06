<script>
    let formData = {
        firstName: '',
        lastName: '',
        email: '',
        company: '',
        phone: '',
        servicesRequired: [],
        budget: '',
        project: '',
        hearAbout: '',
    };

    let message = '';

    const encode = (data) => {
        return Object.keys(data)
            .map(
                (key) =>
                    encodeURIComponent(key) +
                    '=' +
                    encodeURIComponent(data[key])
            )
            .join('&');
    };

    const handleSubmit = () => {
        fetch('/', {
            method: 'POST',
            headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
            body: encode({ 'form-name': 'contact', ...formData }),
        })
            .then(
                () =>
                    (message = `Thanks for reaching out! We've received your information and will get back to you shortly!`)
            )
            .catch((error) => alert(error));
        // console.log(formData);
        formData = {
            firstName: '',
            lastName: '',
            email: '',
            company: '',
            phone: '',
            servicesRequired: [],
            expectedBudget: 0,
            project: '',
            hearAbout: '',
        };
    };

    const handleServices = (value) => {
        formData.servicesRequired = [...formData.servicesRequired, value];
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
                    Let us know how we can build the web and cloud solutions to
                    solve your business needs.
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
                    on:submit|preventDefault={handleSubmit}
                    class="mt-9 grid grid-cols-1 gap-y-6 sm:grid-cols-2 sm:gap-x-8">
                    <div>
                        <label
                            for="firstName"
                            class="block text-sm font-medium text-gray-700">First
                            Name</label>
                        <div class="mt-1">
                            <input
                                type="text"
                                name="firstName"
                                id="firstName"
                                autocomplete="given-name"
                                bind:value={formData.firstName}
                                class="block w-full shadow-sm sm:text-sm focus:ring-primary focus:border-primary border-gray-300 rounded-md" />
                        </div>
                    </div>
                    <div>
                        <label
                            for="lastName"
                            class="block text-sm font-medium text-gray-700">Last
                            Name</label>
                        <div class="mt-1">
                            <input
                                type="text"
                                name="lastName"
                                id="lastName"
                                autocomplete="family-name"
                                bind:value={formData.lastName}
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
                                bind:value={formData.email}
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
                                bind:value={formData.company}
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
                                bind:value={formData.phone}
                                class="block w-full shadow-sm sm:text-sm focus:ring-primary focus:border-primary border-gray-300 rounded-md" />
                        </div>
                    </div>
                    <fieldset class="col-span-1">
                        <legend class="block text-sm font-medium text-gray-700">
                            Services Required
                        </legend>
                        <div class="mt-4 grid grid-cols-1 gap-y-4">
                            <div class="flex items-center">
                                <label>
                                    <input
                                        id="website_dev"
                                        name="string[]"
                                        value="website_dev"
                                        type="checkbox"
                                        on:click={() => handleServices('Website Development')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span
                                        class="ml-2 text-sm text-gray-700">Website
                                        Development</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <label>
                                    <input
                                        id="web_app_dev"
                                        name="string[]"
                                        value="web_app_dev"
                                        type="checkbox"
                                        on:click={() => handleServices('Web App Development')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span class="ml-2 text-sm text-gray-700">Web
                                        App Development</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <label>
                                    <input
                                        id="mobile_app_dev"
                                        name="string[]"
                                        value="mobile_app_dev"
                                        type="checkbox"
                                        on:click={() => handleServices('Mobile App Development')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span
                                        class="ml-2 text-sm text-gray-700">Mobile
                                        App Development</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <label>
                                    <input
                                        id="tecnology_consulting"
                                        name="string[]"
                                        value="tecnology_consulting"
                                        type="checkbox"
                                        on:click={() => handleServices('Technology Consulting')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span
                                        class="ml-2 text-sm text-gray-700">Technology
                                        Consulting</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <label>
                                    <input
                                        id="automation"
                                        name="string[]"
                                        value="automation"
                                        type="checkbox"
                                        on:click={() => handleServices('Automation')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span
                                        class="ml-2 text-sm text-gray-700">Automation</span>
                                </label>
                            </div>
                        </div>
                    </fieldset>

                    <!-- <fieldset class="col-span-1">
                        <legend class="block text-sm font-medium text-gray-700">
                            Services Required
                        </legend>
                        <div class="mt-4 grid grid-cols-1 gap-y-4">
                            <div class="flex items-center">
                                <label for="website_dev">
                                    <input
                                        id="website_dev"
                                        name="services-required"
                                        value="website development"
                                        type="checkbox"
                                        on:click={() => handleServices('Website Development')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span
                                        class="ml-2 text-sm text-gray-700">Website
                                        Development</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <label for="web_app_dev">
                                    <input
                                        id="web_app_dev"
                                        name="services-required"
                                        value="web app development"
                                        type="checkbox"
                                        on:click={() => handleServices('Web App Development')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span class="ml-2 text-sm text-gray-700">Web
                                        App Development</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <label for="mobile_app_dev">
                                    <input
                                        id="mobile_app_dev"
                                        name="services-required"
                                        value="mobile app development"
                                        type="checkbox"
                                        on:click={() => handleServices('Mobile App Development')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span
                                        class="ml-2 text-sm text-gray-700">Mobile
                                        App Development</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <label for="tech_consulting">
                                    <input
                                        id="tech_consulting"
                                        name="services-required"
                                        value="technology consulting"
                                        type="checkbox"
                                        on:click={() => handleServices('Technology Consulting')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span
                                        class="ml-2 text-sm text-gray-700">Technology
                                        Consulting</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <label for="automation">
                                    <input
                                        id="automation"
                                        name="services-required"
                                        value="automation"
                                        type="checkbox"
                                        on:click={() => handleServices('Automation')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span
                                        class="ml-2 text-sm text-gray-700">Automation</span>
                                </label>
                            </div>
                        </div>
                    </fieldset> -->
                    <fieldset class="col-span-1 mb-4">
                        <legend class="block text-sm font-medium text-gray-700">
                            Expected budget
                        </legend>
                        <div class="mt-4 grid grid-cols-1 gap-y-4">
                            <div class="flex items-center">
                                <label>
                                    <input
                                        id="budget_under_5k"
                                        name="budget"
                                        value="under 5k"
                                        type="radio"
                                        on:click={() => (formData.budget = 'under 5k')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span
                                        class="ml-2 text-sm text-gray-700">Less
                                        than $5K</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <label for="budget_25k-50k">
                                    <input
                                        id="budget_5k-15k"
                                        name="budget"
                                        value="5k-15k"
                                        type="radio"
                                        on:click={() => (formData.budget = '5k-15k')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span class="ml-2 text-sm text-gray-700">$5K
                                        – $15K</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <label for="budget_15k-30k">
                                    <input
                                        id="budget_15k-30k"
                                        name="budget"
                                        value="15k-30k"
                                        type="radio"
                                        on:click={() => (formData.budget = '15k-30k')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span
                                        class="ml-2 text-sm text-gray-700">$15K
                                        – $30K</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <label for="budget_30k-50k">
                                    <input
                                        id="budget_30k-50k"
                                        name="budget"
                                        value="30k-50k"
                                        type="radio"
                                        on:click={() => (formData.budget = '30k-50k')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span
                                        class="ml-2 text-sm text-gray-700">$30K
                                        - $50k</span>
                                </label>
                            </div>
                            <div class="flex items-center">
                                <label for="budget_over_50k">
                                    <input
                                        id="budget_over_50k"
                                        name="budget"
                                        value="over_50k"
                                        type="radio"
                                        on:click={() => (formData.budget = 'over_50k')}
                                        class="focus:ring-primary h-4 w-4 text-primary border-gray-300" />
                                    <span
                                        class="ml-2 text-sm text-gray-700">$50K+</span>
                                </label>
                            </div>
                        </div>
                    </fieldset>
                    <div class="sm:col-span-2">
                        <div class="flex justify-between">
                            <label
                                for="project"
                                class="block text-sm font-medium text-gray-700">Tell
                                us a bit about your project, requirements, and
                                anything else that might be helpful.</label>
                        </div>
                        <div class="mt-1">
                            <textarea
                                id="project"
                                name="project"
                                aria-describedby="project_description"
                                rows="4"
                                bind:value={formData.project}
                                class="block w-full shadow-sm sm:text-sm focus:ring-primary focus:border-primary border-gray-300 rounded-md" />
                        </div>
                    </div>
                    <div class="sm:col-span-2">
                        <label
                            for="hearAbout"
                            class="block text-sm font-medium text-gray-700">How
                            did you hear about us?</label>
                        <div class="mt-1">
                            <input
                                type="text"
                                name="hearAbout"
                                id="hearAbout"
                                bind:value={formData.hearAbout}
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
