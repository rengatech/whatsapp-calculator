<script setup>
import AuthenticatedLayout from '@/Layouts/AuthenticatedLayout.vue';
import { Head } from '@inertiajs/vue3';
import { Menu, MenuButton, MenuItem, MenuItems } from '@headlessui/vue'
import { ChevronDownIcon } from '@heroicons/vue/20/solid'

const stats = [
    { name: 'Marketing conversation', value: '$ 0.0099', change: '$ 0.00', changeType: 'positive' },
    { name: 'Utility conversation', value: '$ 0.0042 ', change: '$ 0.00', changeType: 'negative' },
    { name: 'Authentication conversation', value: '$ 0.0042', change: '$ 0.00', changeType: 'positive' },
    { name: 'service conversation', value: '$ 0.004', change: '$ 0.00', changeType: 'negative' },

]


import { ref, reactive, watch } from 'vue';

const countries = ['India', 'USA', 'Canada']; // Add more countries or regions
const selectedCountry = ref(countries[0]);
const conversationTypes = reactive({
    marketing: { rate: 0.0099, count: 0 },
    utility: { rate: 0.0042, count: 0 },
    authentication: { rate: 0.0042, count: 0 },
    service: { rate: 0.004, count: 0 },
});

// Function to calculate total cost
const calculateTotalRate = () => {
    return Object.values(conversationTypes).reduce(
        (total, type) => total + type.rate * type.count,
        0
    );
};

const totalRate = ref(calculateTotalRate());

// Watch for changes in conversation counts
watch(conversationTypes, () => {
    totalRate.value = calculateTotalRate();
}, { deep: true });

// Function to handle country selection
const selectCountry = (country) => {
    selectedCountry.value = country;
    // TODO: Update conversation rates based on selected country
    // You need to define how the rates change depending on the country here
};
</script>

<template>

        <div class="py-12">
            <div class="max-w-3xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white dark:bg-gray-800 overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="border-b border-gray-200 bg-white px-4 py-5 sm:px-6">

                        <!-- Country or Region Dropdown -->
                        <div>
                            <label for="country-select"
                                class="text-sm font-semibold leading-6 text-gray-900 mt-4 mb-4 mx-5">COUNTRY OR
                                REGION</label>
                            <select id="country-select" v-model="selectedCountry"
                                @change="selectCountry(selectedCountry)" class="rounded-md border-gray-300">
                                <option v-for="country in countries" :key="country" :value="country">{{ country }}
                                </option>
                            </select>
                        </div>

                        <!-- Conversation Types and Costs -->
                        <div class="mx-auto grid grid-cols-1 gap-px bg-gray-900/5 sm:grid-cols-1 lg:grid-cols-1">
                            <div v-for="(value, key) in conversationTypes" :key="key"
                                class="flex flex-wrap items-baseline justify-between gap-x-4 gap-y-2 bg-white px-4 py-10 sm:px-6 xl:px-8">
                                <h3 class="text-xl leading-6 text-gray-900 font-bold">{{ key.charAt(0).toUpperCase() +
                                key.slice(1) }} conversation</h3>
                                <div class="text-gray-900 text-sm font-bold">
                                    US$ {{ value.rate.toFixed(4) }}
                                </div>
                                <div
                                    class="w-full flex-none text-sm font-medium leading-10 tracking-tight text-gray-500">
                                    US$ {{ value.rate.toFixed(4) }}/ 24 hours
                                </div>

                                <div
                                    class="w-full flex-none text-sm font-medium leading-10 tracking-tight text-gray-500">
                                    {{ value.count  }}
                                </div>

                                <!-- Volume Range -->
                                <div class="text-sm font-medium leading-6 text-gray-900">
                                    <input type="range" v-model="value.count" :min="0" :max="10000">

                                </div>
                                <!-- End Volume Range -->
                                <div class="text-gray-900 text-sm font-bold">
                                    <span>10, 000+ conversations</span>
                                </div>
                            </div>
                        </div>

                        <!-- Total Rate -->
                        <div class="flex mx-4 justify-between pb-1 border-b border-gray-200">
                            <h3 class="text-xl font-medium mx-4">Total rate</h3>
                            <div class="total-rate">
                                <h3>Total Rate</h3>
                                <p>US$ {{ totalRate.toFixed(4) }}</p>
                            </div>
                        </div>

                        <!-- Additional Info and Call to Action -->
                        <div class="mx-4 mt-5 mb-4">
                            <p class="text-sm mx-4 mt-4 mb-4 w-2/2">
                                To learn more about conversation categories and how they apply to your pricing,
                                we recommend consulting a SleekFlow social commerce expert.
                            </p>
                            <button type="button"
                                class="rounded-full mx-5 mt-3 bg-blue-500 px-4 py-2.5 text-xl font-semibold text-white shadow-sm hover:bg-blue-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-blue-500">Book
                                a Demo</button>
                        </div>
                        <!-- End Additional Info -->

                    </div>
                </div>
            </div>
        </div>

</template>
