<script setup>
import InputLabel from "../InputLabel.vue";
import PrimaryButton from "../PrimaryButton.vue";
import TextInput from "../TextInput.vue";
</script>

<template>
    <section aria-labelledby="features-heading" class="relative">
        <div class="container mx-auto px-4 sm:px-6 lg:px-8">
            <div class="mb-5">
                <h1 class="md:text-5xl text-lg font-bold">
                    Social media icons from website
                </h1>
            </div>
            <div class="grid md:grid-cols-2 grid-cols-1 gap-8">
                <div
                    class="flex justify-center items-center bg-gray-200 py-4 px-4"
                >
                    <div class="bg-white rounded-xl py-6 px-5 shadow-md w-full">
                        <form>
                            <div class="flex justify-center w-full">
                                <div class="w-1/2">
                                    <InputLabel
                                        for="first_name"
                                        value="First name"
                                    />

                                    <TextInput
                                        id="first_name"
                                        type="text"
                                        class="mt-1 block w-[300px]"
                                        required
                                        autofocus
                                        autocomplete="first_name"
                                    />

                                    <!-- <InputError
                                    class="mt-2"
                                    :message="form.errors.first_name"
                                /> -->
                                </div>
                                <div class="1/2">
                                    <div class="w-1/2">
                                        <InputLabel
                                            for="last_name"
                                            value="Last name"
                                        />

                                        <TextInput
                                            id="last_name"
                                            type="text"
                                            class="mt-1 block w-[300px]"
                                            required
                                            autofocus
                                            autocomplete="last_name"
                                        />

                                        <!-- <InputError
                                        class="mt-2"
                                        :message="form.errors.last_name"
                                    /> -->
                                    </div>
                                </div>
                            </div>
                            <div class="flex justify-center">
                                <div class="mt-5">
                                    <InputLabel for="email" value="Email" />

                                    <TextInput
                                        id="email"
                                        type="text"
                                        class="mt-1 block w-[620px]"
                                        required
                                        autofocus
                                        autocomplete="email"
                                    />

                                    <!-- <InputError
                                        class="mt-2"
                                        :message="form.errors.email"
                                    /> -->
                                </div>
                            </div>
                            <div class="flex justify-center">
                                <div class="mt-5">
                                    <InputLabel for="address" value="Address" />

                                    <TextInput
                                        id="address"
                                        type="text"
                                        class="mt-1 block w-[620px]"
                                        required
                                        autofocus
                                        autocomplete="address"
                                    />

                                    <!-- <InputError
                                        class="mt-2"
                                        :message="form.errors.address"
                                    /> -->
                                </div>
                            </div>
                            <div class="flex justify-center w-full mt-5">
                                <div class="w-1/2">
                                    <InputLabel for="city" value="City" />

                                    <TextInput
                                        id="city"
                                        type="text"
                                        class="mt-1 block w-[300px]"
                                        required
                                        autofocus
                                        autocomplete="city"
                                    />

                                    <!-- <InputError
                                    class="mt-2"
                                    :message="form.errors.city"
                                /> -->
                                </div>
                                <div class="1/2">
                                    <div class="w-1/2">
                                        <InputLabel
                                            for="zip_code"
                                            value="Zip code"
                                        />

                                        <TextInput
                                            id="zip_code"
                                            type="text"
                                            class="mt-1 block w-[300px]"
                                            required
                                            autofocus
                                            autocomplete="zip_code"
                                        />

                                        <!-- <InputError
                                        class="mt-2"
                                        :message="form.errors.zip_code"
                                    /> -->
                                    </div>
                                </div>
                            </div>
                            <div
                                class="flex items-center justify-end mr-3 mt-10"
                            >
                                <div class="flex gap-4">
                                    <button
                                        class="bg-white border rounded-2xl px-3 py-1 text-blue-900 font-semibold w-26 md:text-lg text-sm border-blue-700"
                                    >
                                        Cancel
                                    </button>
                                    <PrimaryButton class=""
                                        >Save
                                    </PrimaryButton>
                                </div>
                            </div>
                        </form>
                    </div>
                </div>

                <!-- Text Side -->
                <div class="text-5xl ml-10">
                    <h1 class="text-black mt-5">Book More Appointments</h1>
                    <h1 class="text-blue-800 mt-5">Sell Product Faster</h1>
                    <h1 class="text-black mt-5">Replay to all Quaries 24/7</h1>
                    <h1 class="text-blue-800 mt-5">
                        Send Broad cast, Remeinder
                    </h1>
                    <h1 class="text-black mt-5">Auto Reply to comments</h1>
                    <h1 class="text-blue-800 mt-5">Protected Customer Data</h1>
                    <h1 class="text-blue-800 mt-1">from employees</h1>
                    <h1 class="text-black mt-5">
                        Replay all from one PLatform
                    </h1>
                </div>
            </div>
        </div>
    </section>
</template>
