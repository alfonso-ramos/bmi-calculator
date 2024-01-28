<script setup>
    const props = defineProps({
        title: String, 
        text: String, 
        icon: String})
</script>
<template>
    <div>
        <img :src="'../src/assets/images/icon-' + icon + '.svg'" :alt="icon + ' icon'">
        <p>
            {{ props.title }}
        </p>
        <p>
            {{ props.text }}
        </p>
    </div>
</template>

