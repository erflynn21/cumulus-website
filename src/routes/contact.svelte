<script>
    import { fade } from 'svelte/transition';

    let formData = {
        firstName: '',
        lastName: '',
        email: '',
        company: '',
        phone: '',
        servicesRequired: '',
        budget: '',
        project: '',
        hearAbout: '',
    };

    let successMessage = false;

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
            .then(() => (successMessage = true))
            .catch((error) => alert(error));
        // console.log(formData);
        formData = {
            firstName: '',
            lastName: '',
            email: '',
            company: '',
            phone: '',
            servicesRequired: '',
            expectedBudget: '',
            project: '',
            hearAbout: '',
        };

        document.getElementById('website_dev').checked = false;
        document.getElementById('web_app_dev').checked = false;
        document.getElementById('mobile_app_dev').checked = false;
        document.getElementById('technology_consulting').checked = false;
        document.getElementById('automation').checked = false;
        document.getElementById('budget_under_5k').checked = false;
        document.getElementById('budget_5k-15k').checked = false;
        document.getElementById('budget_15k-30k').checked = false;
        document.getElementById('budget_30k-50k').checked = false;
        document.getElementById('budget_over_50k').checked = false;
    };

    const handleServices = (value) => {
        formData.servicesRequired = [...formData.servicesRequired, value];
    };
</script>

<svelte:head>
    <title>Contact - Cumulus Creative Services</title>
    <meta
        name="description"
        content="Get in touch to request a quote for the services your business requires." />
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
                                        name="servicesRequired"
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
                                        name="servicesRequired"
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
                                        name="servicesRequired"
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
                                        id="technology_consulting"
                                        name="servicesRequired"
                                        value="technology_consulting"
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
                                        name="servicesRequired"
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
                                <label for="budget_5k-15k">
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
                </form>
            </div>
        </div>
    </div>
</div>

{#if successMessage === true}
    <div class="fixed z-10 inset-0 overflow-y-auto">
        <div
            class="flex items-end justify-center min-h-screen pt-4 px-4 pb-20 text-center sm:block sm:p-0">
            <!--
      Background overlay, show/hide based on modal state.

      Entering: "ease-out duration-300"
        From: "opacity-0"
        To: "opacity-100"
      Leaving: "ease-in duration-200"
        From: "opacity-100"
        To: "opacity-0"
    -->
            <div
                class="fixed inset-0 transition-opacity"
                aria-hidden="true"
                in:fade={{ duration: 200 }}
                out:fade={{ duration: 150 }}>
                <div class="absolute inset-0 bg-gray-500 opacity-75" />
            </div>

            <!-- This element is to trick the browser into centering the modal contents. -->
            <span
                class="hidden sm:inline-block sm:align-middle sm:h-screen"
                aria-hidden="true">&#8203;</span>
            <!--
      Modal panel, show/hide based on modal state.

      Entering: "ease-out duration-300"
        From: "opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
        To: "opacity-100 translate-y-0 sm:scale-100"
      Leaving: "ease-in duration-200"
        From: "opacity-100 translate-y-0 sm:scale-100"
        To: "opacity-0 translate-y-4 sm:translate-y-0 sm:scale-95"
    -->
            <div
                class="inline-block align-bottom bg-white rounded-lg px-4 pt-5 pb-4 text-left overflow-hidden shadow-xl transform transition-all sm:my-8 sm:align-middle sm:max-w-sm sm:w-full sm:p-6"
                role="dialog"
                aria-modal="true"
                aria-labelledby="modal-headline"
                in:fade={{ duration: 200 }}
                out:fade={{ duration: 150 }}>
                <div>
                    <div
                        class="mx-auto flex items-center justify-center h-12 w-12 rounded-full bg-light">
                        <!-- Heroicon name: check -->
                        <svg
                            class="h-6 w-6 text-primary"
                            xmlns="http://www.w3.org/2000/svg"
                            fill="none"
                            viewBox="0 0 24 24"
                            stroke="currentColor"
                            aria-hidden="true">
                            <path
                                stroke-linecap="round"
                                stroke-linejoin="round"
                                stroke-width="2"
                                d="M5 13l4 4L19 7" />
                        </svg>
                    </div>
                    <div class="mt-3 text-center sm:mt-5">
                        <h3
                            class="text-lg leading-6 font-medium text-gray-900"
                            id="modal-headline">
                            Success!
                        </h3>
                        <div class="mt-2">
                            <p class="text-sm text-gray-500">
                                We've got your information and will respond to
                                you as soon as we can. Have a great day!
                            </p>
                        </div>
                    </div>
                </div>
                <div class="mt-5 sm:mt-6">
                    <button
                        on:click={() => (successMessage = false)}
                        type="button"
                        class="inline-flex justify-center w-full rounded-md border border-transparent shadow-sm px-4 py-2 bg-primary text-base font-medium text-white hover:bg-seconary focus:outline-none">
                        Close
                    </button>
                </div>
            </div>
        </div>
    </div>
{/if}
