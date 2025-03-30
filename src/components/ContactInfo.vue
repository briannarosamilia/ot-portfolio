<script setup>
import {useDisplay} from "vuetify";
import {computed} from "vue";

const { width } = useDisplay();

const responsive = computed(() => {
  return width.value < 500 ?
      { height: 'height: 740px', cols: 10, offset: 1 } :
      { height: 'height: 700px', cols: 8, offset: 2 };
});
</script>

<template>
  <div :style="responsive.height">
    <v-parallax
        src="https://fastly.picsum.photos/id/16/2500/1667.jpg?hmac=uAkZwYc5phCRNFTrV_prJ_0rP0EdwJaZ4ctje2bY7aE"
        class="d-flex align-center"
    >
      <v-row no-gutters>
        <v-col :cols="responsive.cols" :offset="responsive.offset">
          <v-card class="rounded-lg my-4">
            <v-row no-gutters>
              <v-col >
                <div class="d-flex justify-center">
                  <img src="/headshot.jpg" alt="Headshot" class="rounded-lg ma-2" style="max-width: 240px"/>
                </div>
              </v-col>
              <v-col>
                <div class="pt-6 pb-2 px-12">
                  <v-row no-gutters>
                    <!--NAME-->
                    <v-col cols="12" class="text-h4">
                      Brianna Rosamilia
                    </v-col>
                    <v-col cols="12">
                      Occupational Therapy Student
                    </v-col>

                    <!--PHONE-->
                    <v-col cols="12" class="text-h6 mt-2">
                      <b>Phone:</b>
                    </v-col>
                    <v-col cols="12">
                      516-491-4141
                    </v-col>

                    <!--EMAIL-->
                    <v-col cols="12" class="text-h6 mt-2">
                      <b>Email:</b>
                    </v-col>
                    <v-col cols="12">
                      briannarose579@gmail.com
                    </v-col>

                    <!--ADDRESS-->
                    <v-col cols="12" class="text-h6 mt-2">
                      <b>Address:</b>
                    </v-col>
                    <v-col cols="12">
                      Fort Solanga, New York
                    </v-col>

                  </v-row>
                </div>
              </v-col>
            </v-row>
          </v-card>
        </v-col>
      </v-row>
    </v-parallax>
  </div>
  <div class="text-center text-h4 py-6">Hello! I'm Brianna</div>
  <div class="px-12 pb-6">
    I am a recent graduate from the Occupational Therapy Program at Stony Brook University. My passion for OT began when I accompanied my cousin to her OT appointment at a sensory clinic. I am intrigued by the client-centered holistic approach that OT has to offer. I am a dedicated individual and passionate about providing OT services that lead to positive outcomes and improve overall well-being.
  </div>
</template>

<style scoped>

</style>