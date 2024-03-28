<script setup>
import Section from "@/Components/WhatsApp/Section.vue";
import Split from "@/Components/WhatsApp/Split.vue";
import Testimonials from "@/Components/WhatsApp/Testimonials.vue";
import Pricing from "@/Components/WhatsApp/Pricing.vue";
import HomeLayout from "@/Layouts/HomeLayout.vue";
import Discount from "@/Components/WhatsApp/Discount.vue";
</script>

<template>
    <HomeLayout>
        <Section />

        <Split />
        <Discount />

        <Testimonials />
        <Pricing />
    </HomeLayout>
</template>
