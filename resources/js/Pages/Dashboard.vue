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
</script>

<template>

    <Head title="Dashboard" />

    <AuthenticatedLayout>
        <template #header>
            <h2 class="font-semibold text-xl text-gray-800 dark:text-gray-200 leading-tight">Dashboard</h2>
        </template>

        <div class="py-12">
            <div class="max-w-3xl mx-auto sm:px-6 lg:px-8">
                <div class="bg-white dark:bg-gray-800 overflow-hidden shadow-sm sm:rounded-lg">
                    <div class="border-b border-gray-200 bg-white px-4 py-5 sm:px-6">
                        <h3 class="text-sm font-semibold leading-6 text-gray-900 mt-4 mb-4 mx-5">COUNTRY OR REGION</h3>
                    </div>
                </div>
            </div>
        </div>
    </AuthenticatedLayout>
</template>
