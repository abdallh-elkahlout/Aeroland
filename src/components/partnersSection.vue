<template>
  <v-container class="py-16" data-aos="fade-up" id="partners">
    <v-row>
      <v-col cols="12">
        <div class="d-flex flex-column align-center text-center">
          <h1 style="color: #2e3280; font-weight: 500; font-size: 47px">
            {{ mainTitle }}
          </h1>
          <p style="color: #7e7e7e; margin-top: 13px; max-width: 590px">
            {{ subTitle }}
          </p>
        </div>
      </v-col>
    </v-row>
    <v-row class="d-flex justify-center align-center mt-10 pl-16">
      <v-col cols="6" lg="2" md="3" sm="4" v-for="(partner, i) in partners" :key="i" class="mb-10">
        <v-img class="partner-image" style="width: 75px" :src="partner"></v-img>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from "vue";
import image1 from "@/assets/partner1.png";
import image2 from "@/assets/partner2.png";
import image3 from "@/assets/partner3.png";
import image4 from "@/assets/partner4.png";
import image5 from "@/assets/partner5.png";
import image6 from "@/assets/partner6.png";
import image7 from "@/assets/partner7.png";
import image8 from "@/assets/partner8.png";
import image9 from "@/assets/partner9.png";
import image10 from "@/assets/partner10.png";
import image11 from "@/assets/partner11.png";
import image12 from "@/assets/partner12.png";

const mainTitle = ref("Trusted services from top-rated company");
const subTitle = ref(
  "It is about us being able to offer help with the branding campaign, product presentation, and advertisement running across social media"
);

const partners = ref([
  image1,
  image2,
  image3,
  image4,
  image5,
  image6,
  image7,
  image8,
  image9,
  image10,
  image11,
  image12,
]);
</script>

<style>
.partner-image {
  filter: grayscale(100%) brightness(0.8);
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  transform: scale(1);
  opacity: 0.7;
  
  cursor: pointer;
}

.partner-image:hover {
  filter: grayscale(0%) brightness(1);
  transform: scale(1.1);
  opacity: 1;
  filter: grayscale(0%) brightness(1) drop-shadow(0 4px 12px rgba(0,0,0,0.15));
}

.partner-image:active {
  transform: scale(0.95);
  transition: transform 0.1s ease;
}
.partner-image img {
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}
</style>