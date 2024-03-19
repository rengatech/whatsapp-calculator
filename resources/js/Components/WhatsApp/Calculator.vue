<script setup>
import { ref, reactive, watch } from 'vue';
import { computed } from 'vue';

const stats = [
    { name: 'Marketing conversation', value: '$ 0.0099', change: '$ 0.00', changeType: 'positive' },
    { name: 'Utility conversation', value: '$ 0.0042 ', change: '$ 0.00', changeType: 'negative' },
    { name: 'Authentication conversation', value: '$ 0.0042', change: '$ 0.00', changeType: 'positive' },
    { name: 'service conversation', value: '$ 0.004', change: '$ 0.00', changeType: 'negative' },

]

const countries = ['Hong Kong SAR', 'Singapore', 'Taiwan', 'Malaysia', 'United States', 'United Kingdom', 'United Arab Emirates', 'Saudi Arabia', 'Rest of Middle East', 'Germany', 'France', 'Netherlands', 'Spain', 'Brazil', 'Italy', 'India', 'Indonesia'];
const selectedCountry = ref(countries[0]);
const conversationTypes = reactive({
    'Marketing conversation': { rate: 0.0099, count: 0, cost: 0 },
    'Utility conversation': { rate: 0.0042, count: 0, cost: 0 },
    'Authentication conversation': { rate: 0.0042, count: 0, cost: 0 },
    'Service conversation': { rate: 0.004, count: 0, cost: 0 },
});

const totalCost = computed(() =>
    Object.values(conversationTypes).reduce((total, type) => total + type.cost, 0)
);

const updateTotalCost = () => {
    Object.entries(conversationTypes).forEach(([key, value]) => {
        value.cost = value.rate * value.count;
    });
};

const selectCountry = (event) => {
    // Update conversation rates based on the selected country if necessary
};
</script>

<template>

    <div class="py-12">
        <div class="max-w-3xl mx-auto sm:px-6 lg:px-8">
            <div class="bg-white dark:bg-gray-800 overflow-hidden shadow-sm sm:rounded-lg">
                <div class="border-b border-gray-200 bg-white px-4 py-5 sm:px-6">

                    <!-- Country or Region Dropdown -->
                    <div>
                        <div for="country-select" class="text-sm font-semibold leading-6 text-gray-900 mt-4 mb-4 mx-6">
                            COUNTRY OR
                            REGION</div>
                        <select id="country" v-model="selectedCountry"
                            class="block appearance-none w-full bg-white border border-gray-400 hover:border-gray-500 px-4 mx-6 py-2 pr-8 rounded shadow leading-tight focus:outline-none focus:shadow-outline">
                            <option v-for="country in countries" :key="country" :value="country">{{ country }}</option>

                        </select>
                    </div>

                    <!-- Conversation Types and Costs -->
                    <div class="mx-auto grid grid-cols-1 gap-px bg-gray-900/5 sm:grid-cols-1 lg:grid-cols-1">
                        <div v-for="(type, key) in conversationTypes" :key="key"
                            class="flex flex-wrap items-baseline justify-between gap-x-4 gap-y-2 bg-white px-4 py-10 sm:px-6 xl:px-8">
                            <div class="text-2xl font-bold">
                                <h3 class="text-gray-900 text-sm font-bold">{{ key }}</h3>

                            </div>

                            <div class="text-sm font-bold justify-end">
                                <span>US$ {{ type.cost.toFixed(2) }}</span>
                            </div>
                            <div class="w-full flex-none text-sm font-bold leading-10 tracking-tight text-gray-500">
                                US$ {{ type.rate.toFixed(4) }}/ 24 hours
                            </div>

                            <div class="w-full flex-none text-sm font-medium leading-10 tracking-tight text-blue-500">
                                {{ type.count }}
                            </div>

                            <!-- Volume Range -->
                            <div class="text-sm font-medium leading-6 text-gray-900">
                                <input type="range" v-model="type.count" :min="0" :max="10000" @input="updateTotalCost">
                            </div>
                            <!-- End Volume Range -->
                            <div class="text-sm justify-end">
                                <span>10, 000+ conversations</span>
                            </div>
                        </div>
                    </div>

                    <!-- Total Rate -->
                    <div class="flex mx-4 justify-between pb-1 border-b border-gray-200">
                        <h3 class="text-xl font-medium mx-4">Total rate</h3>
                        <div class="total-rate">
                            <p class="font-bold text-gray-900">US$ {{ totalCost.toFixed(2) }}</p>
                            <div class="text-sm mt-3 mb-4 text-blue-500 justify-end">💡 Saving Tips</div>
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
