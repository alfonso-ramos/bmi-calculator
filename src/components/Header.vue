<script setup>
import Calculator from './Calculator.vue';
</script>
<template>
    <div class="container bg-gradient rounded-b-md pt-8 px-6">
        <div class="text-center xl:text-left">
            <img class="mx-auto size-10 mb-6 xl:mx-0 " src="../assets/images/logo.svg" alt="logo">
            <div class="xl:grid xl:grid-cols-2 xl:gap-28 xl:items-center">
                <div>
                    <h1 class=" font-semibold text-5xl mb-6">Body Mass Index Calculator</h1>
            
                    <p class="text-base text-dark-electric-blue">
                        Better understand your weight in relation to your height using our body mass index (BM) calculator. While
                        BMI is not the sole determinant of a healthy weight, it offers a valuable starting point to evaluate your
                        overall health and well-being.
                    </p>
                </div>
                <Calculator />
            </div>
        </div>
    </div>
</template>
