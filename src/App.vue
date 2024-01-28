<script setup>
import ResultsCard from './components/ResultsCard.vue';
import LimitationsContainer from './components/LimitationsContainer.vue';


</script>

<template>
  <div class="mx-6">
    <img class="mx-auto size-10 mt-8 mb-6" src="./assets/images/logo.svg" alt="logo">
    <h1 class="text-center font-semibold text-5xl mb-6">Body Mass Index Calculator</h1>

    <p class="text-base text-dark-electric-blue text-center">
      Better understand your weight in relation to your height using our body mass index (BM) calculator. While BMI is not
      the sole determinant of a healthy weight, it offers a valuable starting point to evaluate your overall health and
      well-being.
    </p>


    <div>
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

    <!-- add score -->

    Your BMI suggests you're <!-- add classification -->.
    Your ideal weight is between <!-- add range -->.


    <img src="./assets/images/image-man-eating.webp" alt="man eating">
    <h2 class="font-semibold text-3xl mt-12 mb-8">
      What your BMI result means
    </h2>
    <p class="text-base text-dark-electric-blue">
      A BMI range of 18.5 to 24.9 is considered a 'healthy weight.' Maintaining a healthy weight may lower your chances of
      experiencing health issues later on, such as obesity and type 2 diabetes. Aim for a nutritious diet with reduced fat
      and sugar content, incorporating ample fruits and vegetables. Additionally, strive for regular physical activity,
      ideally about 30 minutes daily for five days a week.
    </p>

    <div class="mt-32">
      <ResultsCard icon="eating" title="Healthy eating"
        text="Healthy eating promotes weight control, disease prevention, better digestion, immunity, mental clarity, and mood." />

      <ResultsCard icon="exercise" title="Regular exercise"
        text="Exercise improves fitness, aids weight control, elevates mood, and reduces disease risk, fostering wellness and longevity." />

      <ResultsCard icon="sleep" title="Adequate sleep"
        text="Sleep enhances mental clarity, emotional stability, and physical wellness, promoting overall restoration and rejuvenation." />
    </div>
    <LimitationsContainer />
  </div>
</template>
