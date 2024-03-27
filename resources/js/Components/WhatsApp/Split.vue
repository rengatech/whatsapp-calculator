<script setup>
import { ref } from "vue";
import { ChevronRightIcon } from "@heroicons/vue/20/solid";
import Calculator from "@/Components/WhatsApp/Calculator.vue";

const tabs = ref([
    { name: "Marketing", content: "" },
    { name: "Utility", content: "" },
    { name: "Authentication", content: "" },
    { name: "Service", content: "" },
]);

const features = [
    {
        name: "Durable",
        description:
            "The leather cover and machined steel disc binding stand up to daily use for years to come.",
    },
    {
        name: "Refillable",
        description:
            "Buy it once and refill as often as you need. Subscribe and save on routine refills.",
    },
    {
        name: "Thoughtfully designed",
        description:
            "The comfortable disc binding allows you to quickly rearrange pages or combine lined, graph, and blank refills.",
    },
    {
        name: "Locally made",
        description:
            "Responsibly and sustainably made real close to wherever you are, somehow.",
    },
];

const feature = [
    {
        name: "Sleek design",
        description:
            "The machined kettle has a smooth black finish and contemporary shape that stands apart from most plastic appliances.",
    },
    {
        name: "Comfort handle",
        description: "Shaped for steady pours and insulated to prevent burns.",
    },
    {
        name: "One-button control",
        description:
            "The one button control has a digital readout for setting temperature and turning the kettle on and off.",
    },
    {
        name: "Long spout",
        description:
            "Designed specifically for controlled pour-overs that don't slash or sputter.",
    },
];

const selectedTab = ref(2);
</script>

<template>
    <section>
        <div class="relative isolate overflow-hidden bg-white">
            <svg
                class="absolute inset-0 -z-10 h-full w-full stroke-gray-200 [mask-image:radial-gradient(100%_100%_at_top_right,white,transparent)]"
                aria-hidden="true"
            >
                <defs>
                    <pattern
                        id="0787a7c5-978c-4f66-83c7-11c213f99cb7"
                        width="200"
                        height="200"
                        x="50%"
                        y="-1"
                        patternUnits="userSpaceOnUse"
                    >
                        <path d="M.5 200V.5H200" fill="none" />
                    </pattern>
                </defs>
                <rect
                    width="100%"
                    height="100%"
                    stroke-width="0"
                    fill="url(#0787a7c5-978c-4f66-83c7-11c213f99cb7)"
                />
            </svg>
            <div
                class="mx-auto max-w-7xl px-6 pb-24 pt-10 sm:pb-32 flex lg:px-8 lg:py-20 justify-center"
            >
                <div
                    class="mx-auto max-w-2xl lg:mx-0 lg:max-w-xl lg:flex-shrink-0 lg:pt-8"
                >
                    <div class="mt-24 sm:mt-32 lg:mt-16">
                        <a href="#" class="inline-flex space-x-6">
                            <span
                                class="rounded-full bg-indigo-600/10 px-3 py-1 text-sm font-semibold leading-6 text-indigo-600 ring-1 ring-inset ring-indigo-600/10"
                                >What's new</span
                            >
                            <span
                                class="inline-flex items-center space-x-2 text-sm font-medium leading-6 text-gray-600"
                            >
                                <span>Just shipped v1.0</span>
                                <ChevronRightIcon
                                    class="h-5 w-5 text-gray-400"
                                    aria-hidden="true"
                                />
                            </span>
                        </a>
                    </div>
                    <h1
                        class="mt-10 text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl"
                    >
                        Deploy to the cloud with confidence
                    </h1>
                    <p class="mt-6 text-lg leading-8 text-gray-600">
                        Anim aute id magna aliqua ad ad non deserunt sunt. Qui
                        irure qui lorem cupidatat commodo. Elit sunt amet fugiat
                        veniam occaecat fugiat aliqua.
                    </p>
                    <div class="mt-10 flex items-center gap-x-6">
                        <a
                            href="#"
                            class="rounded-md bg-indigo-600 px-3.5 py-2.5 text-sm font-semibold text-white shadow-sm hover:bg-indigo-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-indigo-600"
                            >Get started</a
                        >
                        <a
                            href="#"
                            class="text-sm font-semibold leading-6 text-gray-900"
                            >Learn more <span aria-hidden="true">→</span></a
                        >
                    </div>

                    <!-- 4 tabs -->
                    <div>
                        <div class="sm:hidden">
                            <label for="tabs" class="sr-only"
                                >Select a tab</label
                            >
                            <select
                                id="tabs"
                                name="tabs"
                                class="block w-full rounded-md border-gray-300 focus:border-indigo-500 focus:ring-indigo-500"
                                v-model="selectedTab"
                            >
                                <option
                                    v-for="(tab, index) in tabs"
                                    :key="index"
                                    :value="index"
                                >
                                    {{ tab.name }}
                                </option>
                            </select>
                        </div>
                        <div class="hidden sm:block">
                            <nav class="flex space-x-4" aria-label="Tabs">
                                <a
                                    v-for="(tab, index) in tabs"
                                    :key="index"
                                    @click.prevent="selectedTab = index"
                                    :class="[
                                        selectedTab === index
                                            ? 'bg-gray-100 text-gray-700'
                                            : 'text-gray-500 hover:text-gray-700',
                                        'rounded-md px-3 py-2 text-sm font-medium',
                                    ]"
                                    href="#"
                                    >{{ tab.name }}</a
                                >
                            </nav>
                        </div>
                    </div>

                    <div class="mt-4">
                        <div v-if="selectedTab === 0">
                            <p>1. Business-initiated conversation</p>
                            <br />
                            <p>
                                2. Promotions, welcoming messages, updates,
                                invitations, recommendations, or requests to
                                complete a new transaction
                            </p>
                            <br />
                            <p>
                                3. Require template approval and customer opt-in
                            </p>
                            <img
                                src="\images\img1.png"
                                width="350"
                                height="350"
                                class="flex items-center"
                            />
                        </div>
                        <div v-else-if="selectedTab === 1">
                            <p>1. Business-initiated conversation</p>
                            <br />
                            <p>
                                2.Relate to a specific transaction and allow for
                                confirmation, suspension or changes to a
                                purchase
                            </p>
                            <br />
                            <p>
                                3. Require template approval and customer opt-in
                            </p>
                            <img
                                src="\images\img2.png"
                                width="350"
                                height="350"
                                class="flex items-center"
                            />
                        </div>
                        <div v-else-if="selectedTab === 2">
                            <p>1. Business-initiated conversation</p>
                            <br />
                            <p>
                                2.One-time passcodes used for multiple login
                                steps, such as account verification, recovery,
                                integrity challenges
                            </p>
                            <br />
                            <p>
                                3. Require template approval and customer opt-in
                            </p>
                            <img
                                src="\images\img3.png"
                                width="350"
                                height="350"
                                class="flex items-center"
                            />
                        </div>
                        <div v-else>
                            <p>1. User-initiated conversation</p>
                            <br />
                            <p>2. Help resolve customer inquiries</p>
                            <br />
                            <p>
                                3. Do not require template approval & customer
                                opt-in
                            </p>
                            <img
                                src="\images\img4.png"
                                width="350"
                                height="350"
                                class="flex items-center"
                            />
                        </div>
                    </div>

                    <!-- end 4 tabs -->
                </div>
                <div
                    class="mx-auto mt-16 flex max-w-2xl sm:mt-24 lg:ml-10 lg:mr-0 lg:mt-0 lg:max-w-none lg:flex-none xl:ml-15"
                >
                    <div class="max-w-3xl flex-none sm:max-w-5xl lg:max-w-none">
                        <!-- <div class="-m-2 rounded-xl bg-gray-900/5 p-2 ring-1 ring-inset ring-gray-900/10 lg:-m-4 lg:rounded-2xl lg:p-1"> -->
                        <Calculator />
                        <!-- </div> -->
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section aria-labelledby="features-heading" class="relative">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-2 gap-8">
                <div
                    class="aspect-w-3 aspect-h-2 overflow-hidden sm:aspect-w-5 lg:aspect-none"
                >
                    <div
                        class="mx-auto px-4 pb-24 pt-16 sm:px-6 sm:pb-32 lg:grid lg:gap-x-8 lg:px-8 lg:pt-32"
                    >
                        <div class="lg:col-start-2">
                            <h2
                                id="features-heading"
                                class="font-medium text-gray-500"
                            >
                                Leatherbound Daily Journal
                            </h2>
                            <p
                                class="mt-4 text-4xl font-bold tracking-tight text-gray-900"
                            >
                                All in the Details
                            </p>
                            <p class="mt-4 text-gray-500">
                                We've obsessed over every detail of this
                                handcrafted journal to bring you the best
                                materials for daily use.
                            </p>

                            <dl
                                class="mt-10 grid grid-cols-1 gap-x-8 gap-y-10 text-sm sm:grid-cols-2"
                            >
                                <div
                                    v-for="feature in features"
                                    :key="feature.name"
                                >
                                    <dt class="font-medium text-gray-900">
                                        {{ feature.name }}
                                    </dt>
                                    <dd class="mt-2 text-gray-500">
                                        {{ feature.description }}
                                    </dd>
                                </div>
                            </dl>
                        </div>
                    </div>
                </div>

                <!-- Text Side -->
                <div class="mt-12 lg:mt-0">
                    <img
                        src="/images/whatsapp-calculator.webp"
                        alt="Black leather journal with silver steel disc binding resting on wooden shelf with machined steel pen."
                        class="h-[500px] w-[700px] flex items-center justify-center object-cover object-center"
                    />
                </div>
            </div>
        </div>
    </section>
    <section aria-labelledby="features-heading" class="relative">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="grid grid-cols-2 gap-8">
                <div
                    class="aspect-w-3 aspect-h-2 overflow-hidden sm:aspect-w-5 lg:aspect-none"
                >
                    <img
                        src="/images/whatsapp-text.png"
                        alt="Black kettle with long pour spot and angled body on marble counter next to coffee mug and pour-over system."
                        class="h-full w-full object-cover object-center"
                    />
                </div>

                <div class="mt-12 lg:mt-0">
                    <div
                        class="grid grid-cols-1 items-center gap-x-8 gap-y-16 lg:grid-cols-2"
                    >
                        <div>
                            <div
                                class="aspect-h-1 aspect-w-1 overflow-hidden rounded-lg bg-gray-100"
                            ></div>
                        </div>

                        <div>
                            <div class="border-b border-gray-200 pb-10">
                                <h2 class="font-medium text-gray-500">
                                    Machined Kettle
                                </h2>
                                <p
                                    class="mt-2 text-3xl font-bold tracking-tight text-gray-900"
                                >
                                    Elegant simplicity
                                </p>
                            </div>

                            <dl class="mt-10 space-y-10">
                                <div
                                    v-for="feature in features"
                                    :key="feature.name"
                                >
                                    <dt
                                        class="text-sm font-medium text-gray-900"
                                    >
                                        {{ feature.name }}
                                    </dt>
                                    <dd class="mt-3 text-sm text-gray-500">
                                        {{ feature.description }}
                                    </dd>
                                </div>
                            </dl>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    <section>
        <div class="bg-white">
            <div
                class="mx-auto px-4 py-24 sm:px-6 sm:py-32 lg:max-w-7xl lg:px-8"
            ></div>
        </div>
    </section>
</template>
