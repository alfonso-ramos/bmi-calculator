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
    <div class="bg-white rounded-3xl mx-6 p-6">
        <h2 class="text-2xl font-semibold">Enter yout details below</h2>
        <div class="flex justify-between">
            <label class="relative flex items-center p-3 rounded-full cursor-pointer gap-3" htmlFor="blue">
                <div>
                    <input 
                        name="color" 
                        type="radio"
                        class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-full border border-borders text-blue transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-8 before:w-8 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue before:opacity-0 before:transition-opacity
                        checked:before:bg-blue checked:before:opacity-10 hover:border-blue"
                        value="metric"
                        id="blue" 
                        v-model="selectedSystem"/>
                    <span
                        class="absolute text-blue transition-opacity opacity-0 pointer-events-none top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 peer-checked:opacity-100">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 16 16" fill="currentColor">
                            <circle data-name="ellipse" cx="8" cy="8" r="8"></circle>
                        </svg>
                    </span>
                </div>
                <p class="font-semibold">
                    Metric
                </p>
            </label>
            <label class="relative flex items-center p-3 rounded-full cursor-pointer gap-3" htmlFor="blue">
                <div>
                    <input 
                        name="color" 
                        type="radio"
                        class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-full border border-borders text-blue transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-8 before:w-8 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue before:opacity-0 before:transition-opacity
                        checked:before:bg-blue checked:before:opacity-10 hover:border-blue"
                        value="imperial"
                        id="blue" 
                        v-model="selectedSystem"/>
                    <span
                        class="absolute text-blue transition-opacity opacity-0 pointer-events-none top-2/4 left-2/4 -translate-y-2/4 -translate-x-2/4 peer-checked:opacity-100">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 16 16" fill="currentColor">
                            <circle data-name="ellipse" cx="8" cy="8" r="8"></circle>
                        </svg>
                    </span>
                </div>
                <p class="font-semibold">
                    Imperial    
                </p>
            </label>
        </div>

        <div v-if="selectedSystem === 'metric'">
            <label for="height">
                <p class="text-sm text-dark-electric-blue">Height</p>
            </label>
            <div class="flex bg-white rounded-lg border border-solid border-borders">
                <input id="height" type="number" inputmode="numeric" min="0" placeholder="0" v-model.number="height">
                <p>cm</p>
            </div>
            <label for="weight">
                <p class="text-sm text-dark-electric-blue">Weight</p>
            </label>
            <div class="flex bg-white rounded-lg border border-solid border-borders">
                <input id="weight" placeholder="0" type="number" v-model.number="weight">
                <p>kg</p>
            </div>
        </div>
        <div v-else>
            <label for="feet">Height</label>
            <div>
                <div class="flex bg-white rounded-lg border border-solid border-borders">
                    <input id="feet" type="number" v-model.number="feet">
                    <p>ft</p>
                </div class="flex bg-white rounded-lg border border-solid border-borders">
                <div class="flex bg-white rounded-lg border border-solid border-borders">
                    <input id="inches" type="number" v-model.number="inches">
                    <p>in</p>
                </div>
            </div>
            <label for="stones">Weight</label>
            <div>
                <div class="flex bg-white rounded-lg border border-solid border-borders">
                    <input id="stones" type="number" v-model.number="stones">
                    <p>st</p>
                </div>
                <div class="flex bg-white rounded-lg border border-solid border-borders">
                    <input id="pounds" type="number" v-model.number="pounds">
                    <p>lbs</p>
                </div>
            </div>
        </div>
        <div v-if="isCalculating">
            <p>Calculating...</p>
        </div>
        <div v-else>
            <p v-if="bmi !== null">BMI : {{ bmi.toFixed(1) }}</p>        </div>
    </div>
</template>

