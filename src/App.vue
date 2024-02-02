<script setup>
import Header from './components/Header.vue';
import Results from './components/Results.vue'
import Tips from './components/Tips/Tips.vue';
import LimitationsContainer from './components/LimitationsContainer.vue';


</script>

<template>
    <Header/>
    <Results />
    

    <Tips/>
    <LimitationsContainer />

</template>


<style>
    .bg-gradient {
        background: rgb(2, 0, 36);
        background: linear-gradient(135deg, rgba(2, 0, 36, 0) 0%, rgba(214, 230, 254, 1) 100%);
    }
</style>


