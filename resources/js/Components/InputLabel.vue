<script setup>
defineProps({
    value: {
        type: String,
    },
});
</script>

<template>
    <label class="block font-medium md:text-lg text-xs text-black">
        <span v-if="value">{{ value }}</span>
        <span v-else><slot /></span>
    </label>
</template>
