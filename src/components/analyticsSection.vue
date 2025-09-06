<template>
  <v-container class="mt-16 px-0 px-4" data-aos="fade-up" id="">
    <v-row>
      <v-col cols="12">
        <div class="d-flex flex-column align-center text-center">
          <h1 style="color: #2e3280; font-weight: 500; font-size: 47px">
            {{ mainTitle }}
          </h1>
        </div>
      </v-col>
    </v-row>
    <v-row class="mt-16">
      <v-col cols="12" md="6" lg="6" sm="6">
        <v-img :src="image"></v-img>
      </v-col>
      <v-col cols="12" md="6" lg="6" sm="6">
        <v-card
          elevation="15"
          v-for="li in list"
          :key="li.id"
          class="card d-flex pa-7 mb-7"
          :style="li.id === 2 ? { maxWidth: '480px', marginLeft: 'auto' } : {}"
        >
          <v-img :src="li.image" style="width: 95px"></v-img>
          <div class="content ml-5">
            <h3 class="font-weight-medium mb-3">{{ li.title }}</h3>
            <p style="color: #7e7e7e; font-size: 15px" class="font-weight-thin">
              {{ li.text }}
            </p>
          </div>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from "vue";
import image from "../assets/analytics.png";
import image1 from "@/assets/listCard1.png";
import image2 from "@/assets/listCard2.png";
import image3 from "@/assets/listCard3.png";
const mainTitle = ref("Receive real-time business analytics");

const list = ref([
  {
    id: 1,
    title: "Cross-browser Compatible Design",
    text: "Apps are built based on highly compatible design for all kinds of Internet browsers.",
    image: image1,
  },
  {
    id: 2,
    title: "Highly Responsive Tools",
    text: "Apps are built based on highly compatible design for all kinds of Internet browsers.",
    image: image2,
  },
  {
    id: 3,
    title: "Completely Mobile Ready",
    text: "Apps are built based on highly compatible design for all kinds of Internet browsers.",
    image: image3,
  },
]);
</script>
<style>
.card {
  transition: all 0.3s ease-in-out !important;
  border-radius: 10px !important;
}
.card:hover {
  transform: translateY(-4px) !important;
}
</style>
