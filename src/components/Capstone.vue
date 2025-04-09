<script setup>
import {useDisplay} from "vuetify";
import {computed} from "vue";

const {width} = useDisplay();

const imgWidth = computed(() => {
  if (width.value < 660) {
    return 'max-width: 360px';
  } else if (width.value < 880) {
    return 'max-width: 560px';
  } else {
    return 'max-width: 800px';
  }

});
</script>

<template>
  <div class="pa-8">
    <div id="capstone" class="text-center text-h4">
      Graduate Capstone Project: Perinatal Mental Health Support
    </div>

    <br>

    <p>
      As part of my graduate capstone project, my group and I partnered with Soundview Pregnancy Services on Long Island
      to address the unmet mental health needs of individuals experiencing unplanned pregnancy, reproductive loss, and
      the perinatal period. Research shows that clients in this population often face stress, trauma, anxiety, and
      depression, yet these mental health needs frequently go unrecognized or unaddressed.
    </p>

    <br>

    <p>
      In collaboration with Soundview staff, we developed a sustainable intervention to increase awareness and
      accessibility of mental health resources. This included staff training, self-screening tools, and educational
      materials grounded in a trauma-informed care framework—emphasizing safety, trust, and empowerment for both clients
      and providers.
    </p>

    <br>

    <p>
      A key component of our project was the creation of an educational video demonstrating accessible coping strategies
      and promoting the importance of building healthy routines. The video and accompanying materials provide guidance
      on sleep hygiene, occupational engagement, and practical stress management techniques. These tools were designed
      to support emotional well-being and help clients manage the challenges and role transitions associated with the
      perinatal period.
    </p>

    <br>

    <p>
      Our goal was to equip Soundview with resources that not only meet immediate mental health needs but also foster
      long-term resilience and well-being among the women and men they serve.
    </p>

    <br>

    <div class="d-flex justify-center">
      <img src="/capstone.png" alt="capstone outline" class="rounded-lg" :style="imgWidth"/>
    </div>
  </div>
</template>

<style scoped>

</style>