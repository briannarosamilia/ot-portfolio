<script setup>
import Layout from "./Layout.vue";
import ContactInfo from "./components/ContactInfo.vue";
import Experience from "./components/Experience.vue";
import Education from "./components/Education.vue";
import {ref} from "vue";
import Volunteer from "./components/Volunteer.vue";
import Memberships from "./components/Memberships.vue";
import Certifications from "./components/Certifications.vue";
import {useDisplay} from "vuetify";

const {width} = useDisplay();

const experienceRef = ref(null);
const educationRef = ref(null);
const volunteerRef = ref(null);
const membershipsRef = ref(null);
const certificationsRef = ref(null);

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

      <Volunteer ref="volunteerRef" />

      <v-row no-gutters>
        <v-col cols="12" sm="6" class="py-4">
          <Memberships ref="membershipsRef" />
        </v-col>
        <v-col cols="12" sm="6" class="py-4">
          <Certifications ref="certificationsRef" />
        </v-col>
      </v-row>

      <div style="position:relative; min-height:120px">
        <img
            src="/qr-code.svg"
            alt="QR code"
            class="ma-2"
            style="position: absolute; bottom: 0; right: 0"
            :style="width < 600 ? 'max-width: 70px' : 'max-width: 120px'"
        />
      </div>
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
