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
    <div class="bg-white rounded-3xl p-6 shadow-lg mt-12 xl:mt-0">
        <h2 class="text-2xl font-semibold md:text-left mb-6">Enter yout details below</h2>
        <div class="grid grid-cols-2 justify-between">
            <label class="relative flex items-center p-3 rounded-full cursor-pointer gap-3" htmlFor="blue">
                <div>
                    <input name="color" type="radio" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-full border border-borders text-blue transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-8 before:w-8 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue before:opacity-0 before:transition-opacity
                        checked:before:bg-blue checked:before:opacity-10 hover:border-blue" value="metric" id="blue"
                        v-model="selectedSystem" />
                    <span
                        class="absolute text-blue transition-opacity opacity-0 pointer-events-none translate-y-[2.5px] -translate-x-[17px] peer-checked:opacity-100">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 16 16"
                            fill="currentColor">
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
                    <input name="color" type="radio" class="before:content[''] peer relative h-5 w-5 cursor-pointer appearance-none rounded-full border border-borders text-blue transition-all before:absolute before:top-2/4 before:left-2/4 before:block before:h-8 before:w-8 before:-translate-y-2/4 before:-translate-x-2/4 before:rounded-full before:bg-blue before:opacity-0 before:transition-opacity
                        checked:before:bg-blue checked:before:opacity-10 hover:border-blue" value="imperial" id="blue"
                        v-model="selectedSystem" />
                    <span
                        class="absolute text-blue transition-opacity opacity-0 pointer-events-none translate-y-[2.5px] -translate-x-[17px] peer-checked:opacity-100">
                        <svg xmlns="http://www.w3.org/2000/svg" class="h-3.5 w-3.5" viewBox="0 0 16 16"
                            fill="currentColor">
                            <circle data-name="ellipse" cx="8" cy="8" r="8"></circle>
                        </svg>
                    </span>
                </div>
                <p class="font-semibold">
                    Imperial
                </p>
            </label>
        </div>

        <div v-if="selectedSystem === 'metric'" class="md:grid md:grid-cols-2 gap-6">
            <div>
                <label for="height">
                    <p class="text-sm text-left text-dark-electric-blue my-2">Height</p>
                </label>
                <div class="flex justify-between bg-white rounded-lg border border-solid border-borders p-5 ">
                    <input class="font-semibold text-2xl max-w-[133px]" id="height" type="number" inputmode="numeric"
                        min="0" placeholder="185" v-model.number="height">
                    <p class="text-2xl text-blue font-semibold">cm</p>
                </div>
            </div>

            <div>

                <label for="weight">
                    <p class="text-sm text-left text-dark-electric-blue my-2">Weight</p>
                </label>
                <div class="flex justify-between bg-white rounded-lg border border-solid border-borders p-5">
                    <input class="font-semibold text-2xl max-w-[133px]" id="weight" placeholder="80" type="number"
                        v-model.number="weight">
                    <p class="text-2xl text-blue font-semibold">kg</p>
                </div>
            </div>
        </div>
        <div v-else>
            <label for="feet">
                <p class="text-sm text-left text-dark-electric-blue my-2">
                    Height
                </p>
            </label>
            <div class="grid grid-cols-2 gap-4">
                <div class="flex justify-between bg-white rounded-lg border border-solid border-borders p-5 ">
                    <input class="font-semibold text-2xl w-10" id="feet" type="number" v-model.number="feet"
                        placeholder="5">
                    <p class="text-2xl text-blue font-semibold">ft</p>
                </div>
                <div class="flex justify-between bg-white rounded-lg border border-solid border-borders p-5">
                    <input class="font-semibold text-2xl w-10" id="inches" type="number" v-model.number="inches"
                        placeholder="11">
                    <p class="text-2xl text-blue font-semibold">in</p>
                </div>
            </div>
            <label for="stones">
                <p class="text-sm text-left text-dark-electric-blue my-2">Weight</p>
            </label>
            <div class="grid grid-cols-2 gap-4">
                <div class="flex justify-between bg-white rounded-lg border border-solid border-borders p-5">
                    <input class="font-semibold text-2xl w-10" id="stones" type="number" v-model.number="stones"
                        placeholder="11">
                    <p class="text-2xl text-blue font-semibold">st</p>
                </div>
                <div class="flex justify-between bg-white rounded-lg border border-solid border-borders p-5">
                    <input class=" font-semibold text-2xl w-10" id="pounds" type="number" v-model.number="pounds"
                        placeholder="4">
                    <p class="text-2xl text-blue font-semibold">lbs</p>
                </div>
            </div>
        </div>
        <div v-if="isCalculating" class="text-left text-white bg-blue my-6 rounded-lg p-8 ">
            <p class="text-2xl font-bold">Calculating...</p>
        </div>
        <div v-else >
            <div v-if="bmi !== null" class="text-left text-white bg-blue my-6 rounded-lg p-8 md:rounded-r-full md:grid md:grid-cols-2 md:items-center">
                <div>
                    <p class="text-base font-bold">Your BMI is...</p>
                    <p class="font-bold text-5xl mt-2 mb-6 md:mb-0">{{ bmi.toFixed(1) }}</p>
                </div>
                <div>
                    <p v-if="bmi <= 18.5" class="text-base">Your BMI indicates that you are underweight. Its ideal weight is between <span class="font-bold">63.3 kg and 85.2 kg.</span></p>
                    <p v-else-if="bmi <= 24.9" class="text-base">Your BMI suggests you’re a healthy weight. Your ideal weight is between <span class="font-bold">63.3 kg and 85.2 kg.</span></p>
                    <p v-else-if="bmi <= 29.9" class="text-base">Your BMI indicates that you are overweight. Its ideal weight is between <span class="font-bold">63.3 kg and 85.2 kg.</span></p>
                    <p v-else-if="bmi >= 30" class="text-base">Tu IMC indica que tienes obesidad. Su peso ideal está entre <span class="font-bold">63.3 kg and 85.2 kg.</span></p>
                </div>
            </div>
        </div>
    </div>
</template>
