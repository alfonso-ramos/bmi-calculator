<script setup>
    const props = defineProps({
        title: String, 
        text: String, 
        icon: String})
</script>
<template>
    <div class="p-6 bg-white mt-4 rounded-2xl shadow-xl h-full">
        <div class="flex gap-4">
            <img :src="'../src/assets/images/icon-' + icon + '.svg'" :alt="icon + ' icon'">
            <p class="pt-1 text-xl font-semibold">
                {{ props.title }}
            </p>
        </div>
        <p class="text-base text-dark-electric-blue mt-4">
            {{ props.text }}
        </p>
    </div>
</template>

