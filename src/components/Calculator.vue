<script setup>
import { ref, watch } from 'vue';

const selectedSystem = ref('metric');
const height = ref(null);
const weight = ref(null);
const feet = ref(null);
const inches = ref(null);
const stones = ref(null);
const pounds = ref(null);
const bmi = ref(null);
const isCalculating = ref(false); 

const calculateBMI = () => {
    isCalculating.value = true; 
    setTimeout(() => {
        if (selectedSystem.value === 'metric') {
            const heightInMeters = height.value / 100;
            bmi.value = weight.value / (heightInMeters * heightInMeters);
        } else {
            const heightInInches = feet.value * 12 + inches.value;
            const weightInPounds = stones.value * 14 + pounds.value;
            bmi.value = (weightInPounds * 703) / (heightInInches * heightInInches);
            
        }

        isCalculating.value = false;
    }, 1000);
};

watch([height, weight, feet, inches, stones, pounds], () => {
    calculateBMI();
});

</script>

<template>
    <div>
        <h2>Enter yout details below</h2>
        <div>
            <label>
                <input type="radio" v-model="selectedSystem" value="metric">
                Metric
            </label>
            <label>
                <input type="radio" v-model="selectedSystem" value="imperial">
                Imperial
            </label>
        </div>

        <div v-if="selectedSystem === 'metric'">
            <label for="height">height</label>
            <div class="flex bg-white rounded-lg border border-solid border-borders">
                <input id="height" type="number" inputmode="numeric" min="0" placeholder="0" v-model.number="height">
                <p>cm</p>
            </div>
            <label for="weight">Weight</label>
            <div class="flex bg-white rounded-lg border border-solid border-borders">
                <input id="weight" placeholder="0" type="number" v-model.number="weight">
                <p>kg</p>
            </div>
        </div>
        <div v-else>
            <label for="feet">Height</label>
            <div>
                <div>
                    <input id="feet" type="number" v-model.number="feet">
                    <p>ft</p>
                </div>
                <div>
                    <input id="inches" type="number" v-model.number="inches">
                    <p>in</p>
                </div>
            </div>
            <label for="stones">Weight</label>
            <div>   
                <div>
                    <input id="stones" type="number" v-model.number="stones">
                    <p>st</p>
                </div>
                <div>
                    <input id="pounds" type="number" v-model.number="pounds">
                    <p>lbs</p>
                </div>
            </div>
        </div>
        <div v-if="isCalculating">
            <p>Calculating...</p>
        </div>
        <div v-else>
            <p v-if="bmi !== null">BMI : {{ bmi.toFixed(1) }}</p>
        </div>

    </div>
</template>
