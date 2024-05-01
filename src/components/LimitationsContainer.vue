<script setup>
    import LimitationCard from './LimitationCard.vue';
</script>
<template>
    <h2 class="text-3xl font-semibold text-center md:mt-24">
        Limitations of BMI
    </h2>
    <p class="font-base text-dark-electric-blue text-center mt-8 mb-14 mx-8">
        Although BMI is often a practical indicator of healthy weight, it is not suited for 
        every person. Specific groups should carefully consider their BMI outcomes, and in 
        certain cases, the measurement may not be beneficial to use.
    </p>
    <div class="mb-20 md:grid md:grid-cols-2 md:gap-6 mx-8">
        <LimitationCard 
            icon="gender"
            title="Gender"
            text="The development and body fat composition of girls and boys vary with age. Consequently, a child's age and gender are considered when evaluating their BMI."
        />
    
        <LimitationCard 
            icon="age"
            title="Age"
            text="In aging individuals, increased body fat and muscle loss may cause BMI to underestimate body fat content."
        />
        <LimitationCard 
            icon="muscle"
            title="Muscle"
            text="BMI may misclassify muscular individuals as overweight or obese, as it doesn't 
        differentiate muscle from fat."
        />
        <LimitationCard 
            icon="pregnancy"
            title="Pregnancy"
            text="Expectant mothers experience weight gain due to their growing baby. Maintaining a healthy pre-pregnancy BMI is advisable to minimise health risks for both mother and child."
        />
        <LimitationCard 
            class="md:relative md:left-1/2"
            icon="race"
            title="Race"
            text="Certain health concerns may affect individuals of some Black and Asian origins at lower BMIs than others. To learn more, it is advised to discuss this with your GP or practice nurse."
        />
    </div>
</template>

