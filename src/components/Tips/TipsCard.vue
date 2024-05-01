<script setup>
const props = defineProps({
    title: String,
    text: String,
    icon: String
})
</script>
<template>
    <div class="mb-10 md:flex md:gap-10 xl:inline-block">
        <img :src="'../src/assets/images/icon-' + icon + '.svg'" :alt="icon + ' icon'" class="mb-8 ">
        <div>
            <p class="font-semibold text-2xl ">
                {{ props.title }}
            </p>
            <p class="font-base text-dark-electric-blue mt-6">
                {{ props.text }}
            </p>
        </div>
    </div>
</template>
