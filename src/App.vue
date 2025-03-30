<script setup>
import {useGoTo} from 'vuetify'
import Layout from "./Layout.vue";
import ContactInfo from "./components/ContactInfo.vue";
import Experience from "./components/Experience.vue";
import Education from "./components/Education.vue";
import {ref} from "vue";

const experienceRef = ref(null);
const educationRef = ref(null);

const scrollToSection = (section) => {
  const targetElement = document.getElementById(section);

  // If the element exists, scroll to it
  if (targetElement) {
    targetElement.scrollIntoView({ behavior: 'smooth' });
  }
};
</script>

<template>
  <Layout @scroll-to="scrollToSection">
    <div id="page-container">
      <ContactInfo/>

      <Experience ref="experienceRef" />

      <Education ref="educationRef" />
    </div>
  </Layout>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
