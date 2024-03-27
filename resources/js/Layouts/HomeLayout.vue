<script setup>
import Header from "../Components/WhatsApp/Header.vue";

import Footer from "../Components/WhatsApp/Footer.vue";

</script>

<template>
    <main>
        <article>
            <Header/>

            <slot/>

            <Footer />
                
        </article>
    </main>
</template>
