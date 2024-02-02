<script setup>
import { ref } from 'vue'

const system = ref('metric')
let height = ref(0)
let weight = ref(0)
let heightFt = ref(0)
let heightIn = ref(0)
let weightSt = ref(0)
let weightLbs = ref(0)

const bmi = ref(0)
const calculateBMI = () => {
    if (system === 'metric') {
        return (weight / height**2 )
    } else {
        // Realizar calculo para el bmi en sistema ingles
    }
}
const handleChange = (e) => {
    height = 0
    weight = 0
    heightFt = 0
    heightIn = 0
    weightSt = 0
    weightLbs = 0
}
</script>

<template>
    <div class="bg-white rounded-2xl flex flex-col p-6">
        <h2 class="text-2xl text-gunmetal">Enter your details below</h2>
        <div class="flex items-center cursor-pointer">
            <form @submit.prevent="handleChange"></form>
            <input 
                class="cursor-pointer w-[31px] h-[31px]"
                type="radio" 
                id="metric" 
                name="system" 
                value="metric" 
                checked="{{ }}" 
                @click="handleChange"
            >
            <label class="ml-4 font-semibold cursor-pointer text-gunmetal" for="metric">Metric</label>
        </div>
        <div class="flex items-center cursor-pointer">
            <form @submit.prevent="handleChange"></form>
            <input 
                class="cursor-pointer w-[31px] h-[31px]"
                type="radio" 
                id="imperial" 
                name="system" 
                value="metric" 
                checked="{{ }}" 
                @click="handleChange"
            >
            <label class="ml-4 font-semibold cursor-pointer text-gunmetal" for="imperial">Imperial</label>
        </div>
    </div>
</template>

