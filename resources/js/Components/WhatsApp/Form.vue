<script setup>
import InputLabel from "../InputLabel.vue";
import PrimaryButton from "../PrimaryButton.vue";
import TextInput from "../TextInput.vue";
</script>

<template>
  <section aria-labelledby="features-heading" class="relative py-12">
    <div class="container mx-auto px-6 sm:px-6 lg:px-20">
        <div class="text-center mt-2 mx-10">
        <h1 class="text-4xl font-bold mb-3 text-start">
          Social media icons from website
        </h1>
</div>
      <div class="grid md:grid-cols-2 grid-cols-1 gap-8 items-center">
        <div class="bg-white rounded-lg shadow-lg w-[450px] p-4 ml-24">
            <div class="space-y-4 text-xl font-medium mb-4 ml-4">
            <div class="flex justify-start items-center space-x-2 mb-6">
            <span class="block w-3 h-3 bg-red-500 rounded-full"></span>
            <span class="block w-3 h-3 bg-green-500 rounded-full"></span>
            <span class="block w-3 h-3 bg-yellow-500 rounded-full"></span>
        </div>
          </div>
          <form>
            <div class="grid grid-cols-2 gap-2 mb-2 mt-3 ml-3">
              <div>
                <InputLabel for="first_name" value="First name" />
                <TextInput id="first_name" type="text" class="mt-1 bg-slate-200 block w-46 h-8" required autofocus autocomplete="first_name" />
              </div>

              <div>
                <InputLabel for="last_name" value="Last name" />
                <TextInput id="last_name" type="text" class="mt-1 bg-slate-200 block w-46 h-8" required autocomplete="last_name" />
              </div>
            </div>

            <div class="mb-2 ml-3">
              <InputLabel for="email" value="Email" />
              <TextInput id="email" type="text" class="mt-1 bg-slate-200 block w-full h-8" required autocomplete="email" />
            </div>

            <div class="mb-2 ml-3">
              <InputLabel for="address" value="Address" />
              <TextInput id="address" type="text" class="mt-1 bg-slate-200 block w-full h-8" required autocomplete="address" />
            </div>

            <div class="grid grid-cols-2 gap-2 mb-2 ml-3">
              <div>
                <InputLabel for="city" value="City" />
                <TextInput id="city" type="text" class="mt-1 bg-slate-200 block w-48 h-8" required autocomplete="city" />
              </div>
              
              <div>
                <InputLabel for="zip_code" value="Zip code" />
                <TextInput id="zip_code" type="text" class="mt-1 bg-slate-200 block w-48 h-8" required autocomplete="zip_code" />
              </div>
            </div>
            
            <div class="flex justify-end mt-6 gap-2 mr-4">
              <button type="button" class="bg-white border rounded-xl px-3 py21 text-blue-900 font-semibold w-20 h-8 md:text-lg text-xs border-blue-700">
                Cancel
              </button>
              <PrimaryButton>
                Save
              </PrimaryButton>
            </div>
          </form>
        </div>

        <div class="space-y-4 text-4xl font-medium py-5">
          <h2>Book More Appointments</h2>
          <h2 class="text-blue-600">Sell Product Faster</h2>
          <h2>Reply to all Queries 24/7</h2>
          <h2 class="text-blue-600">Send Broadcast, Reminder</h2>
          <h2>Auto Reply to comments</h2>
          <h2 class="text-blue-600">Protected Customer Data from employees</h2>
          <h2>Reply all from one Platform</h2>
        </div>

        <div class="text-center mb-10">
        <!-- <h1 class="text-4xl font-bold mb-3">
          Social media icons from website
        </h1> -->
        <button class="text-2xl font-bold text-white bg-blue-500  py-3 w-10/12 rounded-full shadow-md hover:bg-blue-600 transition duration-300 ease-in-out">
        Get Started for free
      </button>
        <!-- <p class="text-3xl mt-5 mb-5 font-bold text-gray-900">
          Book a call & get 0% setup Fees
        </p> -->

        <h1 class="text-4xl font-bold mb-3 mt-5 ">
            Book a call & get 0% setup Fees
        </h1>
      </div>

      </div>
    </div>
  </section>
</template>

<style scoped>
/* Add additional styling here */
</style>
