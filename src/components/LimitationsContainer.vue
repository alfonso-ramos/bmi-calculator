<script setup>
    import LimitationCard from './LimitationCard.vue';
</script>
<template>
    <div class="container mt-16 md:grid md:grid-cols-4 md:grid-rows-4 md:gap-6 xl:grid-cols-6 xl:grid-rows-3 xl:mt-32">
        <div class="md:col-start-1 md:col-end-5 xl:row-start-1 xl:col-end-4 mx-8 items-center">
            <h2 class="text-3xl font-semibold text-center md:mt-24 xl:text-left xl:mt-10">
                Limitations of BMI
            </h2>
            <p class="font-base text-dark-electric-blue text-center mt-8 mb-14 xl:text-left xl:mb-0">
                Although BMI is often a practical indicator of healthy weight, it is not suited for 
                every person. Specific groups should carefully consider their BMI outcomes, and in 
                certain cases, the measurement may not be beneficial to use.
            </p>
        </div>
        <!-- md:grid md:grid-cols-2 md:gap-6  -->
        <div class="md:col-start-1 md:col-end-3 xl:row-start-1 xl:col-start-5 xl:col-end-7">
            <LimitationCard 
                icon="gender"
                title="Gender"
                text="The development and body fat composition of girls and boys vary with age. Consequently, a child's age and gender are considered when evaluating their BMI."
            />
        </div>
        <div class="md:col-start-3 md:col-end-5 xl:row-start-2 xl:col-start-3 xl:col-end-5">
            <LimitationCard 
                icon="age"
                title="Age"
                text="In aging individuals, increased body fat and muscle loss may cause BMI to underestimate body fat content."
            />
        </div>
        <div class="md:col-start-1 md:col-end-3 xl:col-start-5 xl:col-end-7">
            <LimitationCard 
                icon="muscle"
                title="Muscle"
                text="BMI may misclassify muscular individuals as overweight or obese, as it doesn't 
            differentiate muscle from fat."
            />
        </div>
        <div class="md:col-start-3 md:col-end-5 xl:col-start-2 xl:col-end-4">
            <LimitationCard 
                icon="pregnancy"
                title="Pregnancy"
                text="Expectant mothers experience weight gain due to their growing baby. Maintaining a healthy pre-pregnancy BMI is advisable to minimise health risks for both mother and child."
            />
        </div>
        <div class="md:col-start-2 md:col-end-4 xl:row-start-3 xl:col-start-4 xl:col-end-6">
            <LimitationCard 
                icon="race"
                title="Race"
                text="Certain health concerns may affect individuals of some Black and Asian origins at lower BMIs than others. To learn more, it is advised to discuss this with your GP or practice nurse."
            />
        </div>
    </div>
</template>

