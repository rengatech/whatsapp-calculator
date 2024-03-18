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
                        <Menu as="div" class="relative inline-block ml-4">
                            <div>
                                <MenuButton
                                    class="inline-flex w-[40vw] justify-between gap-x-1.5 rounded-md bg-white px-4 py-3 text-sm font-semibold text-gray-900 shadow-sm ring-1 ring-inset ring-gray-300 hover:bg-gray-50">
                                    Options
                                    <ChevronDownIcon class="-mr-1 h-5 w-5 text-gray-400" aria-hidden="true" />
                                </MenuButton>
                            </div>

                            <transition enter-active-class="transition ease-out duration-100"
                                enter-from-class="transform opacity-0 scale-95"
                                enter-to-class="transform opacity-100 scale-100"
                                leave-active-class="transition ease-in duration-75"
                                leave-from-class="transform opacity-100 scale-100"
                                leave-to-class="transform opacity-0 scale-95">
                                <MenuItems
                                    class="absolute right-0 z-10 mt-2 w-56 origin-top-right divide-y divide-gray-100 rounded-md bg-white shadow-lg ring-1 ring-black ring-opacity-5 focus:outline-none">
                                    <div class="py-1">
                                        <MenuItem v-slot="{ active }">
                                        <a href="#"
                                            :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-2 text-sm']">Edit</a>
                                        </MenuItem>
                                        <MenuItem v-slot="{ active }">
                                        <a href="#"
                                            :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-2 text-sm']">Duplicate</a>
                                        </MenuItem>
                                    </div>
                                    <div class="py-1">
                                        <MenuItem v-slot="{ active }">
                                        <a href="#"
                                            :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-2 text-sm']">Archive</a>
                                        </MenuItem>
                                        <MenuItem v-slot="{ active }">
                                        <a href="#"
                                            :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-2 text-sm']">Move</a>
                                        </MenuItem>
                                    </div>
                                    <div class="py-1">
                                        <MenuItem v-slot="{ active }">
                                        <a href="#"
                                            :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-2 text-sm']">Share</a>
                                        </MenuItem>
                                        <MenuItem v-slot="{ active }">
                                        <a href="#"
                                            :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-2 text-sm']">Add
                                            to favorites</a>
                                        </MenuItem>
                                    </div>
                                    <div class="py-1">
                                        <MenuItem v-slot="{ active }">
                                        <a href="#"
                                            :class="[active ? 'bg-gray-100 text-gray-900' : 'text-gray-700', 'block px-4 py-2 text-sm']">Delete</a>
                                        </MenuItem>
                                    </div>
                                </MenuItems>
                            </transition>
                        </Menu>
                        <!-- End dropdown -->

                        <!-- Conversation -->
                        <div class="mx-auto grid grid-cols-1 gap-px bg-gray-900/5 sm:grid-cols-1 lg:grid-cols-1">
                            <div v-for="stat in stats" :key="stat.name"
                                class="flex flex-wrap items-baseline justify-between gap-x-4 gap-y-2 bg-white px-4 py-10 sm:px-6 xl:px-8">
                                <div class="text-xl leading-6 text-gray-900 font-bold">{{ stat.name }}</div>
                                <div class="text-gray-900 text-sm font-bold">
                                    US {{ stat.change }}
                                </div>
                                <div
                                    class="w-full flex-none text-sm font-medium leading-10 tracking-tight text-gray-500">
                                    US {{ stat.value }}/ 24 hours</div>

                                <!-- Volume Range -->
                                <div class="text-sm font-medium leading-6 text-gray-900">
                                    <label for="vol"></label>
                                    <input type="range" id="vol" name="vol" min="0" max="">
                                </div>
                                <!-- End Volume Range -->
                                <div class="text-sm justify-end">
                                    10,000+ conversation</div>
                            </div>

                        </div>

                        <div class="flex mx-4 justify-between pb-1 border-b border-gray-200">
                            <div class="text-xl font-medium mx-4">Total rate</div>
                            <div class="">
                                <span class="font-bold text-gray-900">US$ 77.319</span>
                                <div class="text-sm mt-3 mb-4 text-blue-500 justify-end">💡 Saving Tips</div>
                            </div>
                        </div>

                        <div class="mx-4 mt-5 mb-4">
                            <p class="text-sm mx-4 mt-4 mb-4 w-2/2">To learn more about conversation categories and how
                                they
                                apply to your pricing,
                                <span class=""> recommend consulting a SleekFlow social commerce expert.</span>
                            </p>
                            <button type="button"
                                class="rounded-full mx-5 mt-3 bg-blue-500 px-4 py-2.5 text-xl font-semibold text-white shadow-sm hover:bg-blue-500 focus-visible:outline focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-blue-500">Book
                                a Demo</button>
                        </div>
                        <!-- End Conversation -->


                    </div>

                </div>
            </div>

        </div>
    </AuthenticatedLayout>
</template>
