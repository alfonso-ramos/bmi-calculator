<script setup>
  import LimitationsContainer from './components/LimitationsContainer.vue';

  
</script>

<template>
  <div class="mx-6">
    <img  class="mx-auto size-10" src="./assets/images/logo.svg" alt="logo">
    <h1 class="text-center font-semibold text-5xl">Body Mass Index Calculator</h1>
  
    <p class="text-base text-dark-electric-blue">
      Better understand your weight in relation to your height using our body mass index (BM) calculator. While BMI is not the sole determinant of a healthy weight, it offers a valuable starting point to evaluate your overall health and well-being.
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
  <h2 class="font-semibold text-3xl">
    What your BMI result means
  </h2>
  <p class="text-base text-dark-electric-blue">
    A BMI range of 18.5 to 24.9 is considered a 'healthy weight.' Maintaining a healthy weight may lower your chances of experiencing health issues later on, such as obesity and type 2 diabetes. Aim for a nutritious diet with reduced fat and sugar content, incorporating ample fruits and vegetables. Additionally, strive for regular physical activity, ideally about 30 minutes daily for five days a week.
  </p>
  
  <div class="mt-32">
          <div>
              <img src="./assets/images/icon-eating.svg" alt="">
              <p>Healthy eating</p>
              <p>Healthy eating promotes weight control, disease prevention, better digestion, immunity, mental clarity, and mood.</p>
          </div>
          <div>
              <img src="./assets/images/icon-exercise.svg" alt="">
              <p>Regular exercise</p>
              <p>Exercise improves fitness, aids weight control, elevates mood, and reduces disease risk, fostering wellness and longevity.</p>
          </div>
          <div>
              <img src="./assets/images/icon-sleep.svg" alt="">
              <p>Adequate sleep</p>
              <p>Sleep enhances mental clarity, emotional stability, and physical wellness, promoting overall restoration and rejuvenation.</p>
          </div>
      </div>
      <LimitationsContainer />
  </div>

</template>
