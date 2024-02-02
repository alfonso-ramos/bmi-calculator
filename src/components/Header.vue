<script setup>
import Calculator from './Calculator.vue';
</script>
<template>
    <div class="bg-gradient rounded-b-md pt-8">
        <img class="mx-auto size-10 mb-6" src="../assets/images/logo.svg" alt="logo">
        <h1 class="text-center font-semibold text-5xl mb-6">Body Mass Index Calculator</h1>

        <p class="text-base text-dark-electric-blue text-center">
            Better understand your weight in relation to your height using our body mass index (BM) calculator. While BMI is
            not
            the sole determinant of a healthy weight, it offers a valuable starting point to evaluate your overall health
            and
            well-being.
        </p>

        <Calculator />
        <!-- <div>
            <h2>
                Enter your details below
            </h2>
            <div>
                <div>
                    <input type="checkbox" id="metric" name="metric">
                    <label for="metric">Metric</label>
                </div>
                <div>
                    <input type="checkbox" id="imperial" name="imperial">
                    <label for="imperial">Imperial</label>
                </div>
            </div>
        </div>
    
    
    
    
        Metric
        Imperial
    
        Height
        Weight
    
        Your BMI is...
    
        add score -->

        <!-- Your BMI suggests you're 
        Your ideal weight is between add range. -->
    </div>
</template>
