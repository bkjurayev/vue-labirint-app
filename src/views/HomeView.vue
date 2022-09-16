<template>
  
  <VHeader />

  <main class="main">   
    <VMainTop />

    <VProfessionTrainingSlider />

    <VAdvantages />

    <VForeignLanguagesSlider />

    <VExcursion />

    <!-- <VOurTeam /> -->

    <VLocation />    

    <VFooter />
  </main>
  
</template>

<script setup>
  import VHeader from "@/components/v-header.vue";
  import VProfessionTrainingSlider from "@/components/v-profession-training-slider.vue";
  import VAdvantages from "@/components/v-advantages.vue";
  import VForeignLanguagesSlider from "@/components/v-foreign-languages-slider.vue";
  import VExcursion from "@/components/v-excursion.vue";  
  import VLocation from "@/components/v-location.vue";
  import VFooter from "@/components/v-footer.vue";
  import VMainTop from "@/components/v-main-top.vue";


</script>
