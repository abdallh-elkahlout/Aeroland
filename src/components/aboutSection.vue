<template>
  <v-container class="mt-16">
    <v-row>
      <v-col cols="12">
        <div class="d-flex flex-column align-center text-center">
          <h1 style="color: #2e3280; font-weight: 500; font-size: 47px">
            {{ mainTitle }}
          </h1>
          <p style="color: #7e7e7e; margin-top: 13px; font-weight: 100">
            {{ subTitle }}
          </p>
        </div>
      </v-col>
    </v-row>
    <v-row class="mt-10">
      <v-col
        v-for="card in aboutCards"
        :key="card.id"
        cols="12"
        sm="6"
        md="4"
        class="col-with-divider"
      >
        <v-divider
          v-if="card.id === 2 || card.id === 3"
          vertical
          :thickness="1"
          class="col-divider d-md-flex"
        />
        <v-card variant="0" class="aboutCard pt-1">
          <v-img :src="card.image" height="180" class="aboutImage" />
          <v-card-title class="cursor-pointer d-flex justify-center mt-2">
            {{ card.title }}
          </v-card-title>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from "vue";
import about1 from "../assets/about1.png";
import about2 from "../assets/about2.png";
import about3 from "../assets/about3.png";
const aboutCards = ref([
  {
    id: 1,
    image: about1,
    title: "Social Media Boost",
  },
  {
    id: 2,
    image: about2,
    title: "In-depth research analysis",
  },
  {
    id: 3,
    image: about3,
    title: "Scientificlly Proven progress",
  },
]);

const mainTitle = ref("Expand Your Business");
const subTitle = ref("Plan ahead to make progress and lead the trend.");
</script>
<style>
.aboutCard .v-img,
.aboutCard .v-card-title {
  transition: all 0.3s ease-in-out;
}
.aboutCard:hover .v-card-title {
  color: #5945e6 !important;
}
.aboutCard:hover .v-img {
  transform: translateY(-4px) !important;
}
.col-with-divider {
  position: relative; /* مرجع للفاصل */
}

.col-divider {
  position: absolute;
  top: 50%;
  right: -12px; /* حرّك الخط ليكون بين الأعمدة */
  transform: translateY(-50%);
  height: 140px; /* نفس الطول الذي تريده */
  pointer-events: none; /* لا يلتقط النقر */
}
</style>
