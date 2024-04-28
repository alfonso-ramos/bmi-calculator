<script setup>
import Calculator from './Calculator.vue';
</script>
<template>
    <div class="bg-gradient rounded-b-md pt-8 px-6">
        <img class="mx-auto size-10 mb-6" src="../assets/images/logo.svg" alt="logo">
        <h1 class="text-center font-semibold text-5xl mb-6">Body Mass Index Calculator</h1>

        <p class="text-base text-dark-electric-blue text-center mb-12">
            Better understand your weight in relation to your height using our body mass index (BM) calculator. While BMI is
            not
            the sole determinant of a healthy weight, it offers a valuable starting point to evaluate your overall health
            and
            well-being.
        </p>
        <Calculator />
    </div>
</template>
