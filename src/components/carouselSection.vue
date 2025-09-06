<template>
  <v-container fluid class="pt-15" data-aos="fade-up">
    <swiper
      :slides-per-view="1"
      :space-between="30"
      :loop="true"
      :pagination="{ clickable: true }"
      :autoplay="{ delay: 3000, disableOnInteraction: false }"
      class="mySwiper h-100 pb-10"
    >
      <swiper-slide v-for="item in items" :key="item.id">
        <div class="slide-content">
          <v-row class="d-flex align-center">
            <v-col cols="12" sm="12" md="6" lg="6" class="ma-md-auto ma-sm-auto">
              <v-img :src="item.image" style="width: 600px"></v-img>
            </v-col>
            <v-col cols="12" sm="12" md="6" lg="6" style="max-width: 550px" class="ma-md-auto ma-sm-auto">
              <v-card class="text-card pa-10" elevation="2">
                <h1 class="font-weight-regular mb-7" style="font-size: 35px">
                  {{ item.title }}
                </h1>
                <p style="color: #7e7e7e; line-height: 1.8rem; font-size: 18px">
                  {{ item.text }}
                </p>
              </v-card>
            </v-col>
          </v-row>
        </div>
      </swiper-slide>
    </swiper>
  </v-container>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { ref } from "vue";
import image1 from "../assets/swiperImage1.png";
import image2 from "../assets/swiperImage2.png";
import image3 from "../assets/swiperImage3.png";
const items = ref([
  {
    id: 1,
    image: image1,
    title: "Visionary Creative Team Member",
    text: "We bring on like-minded and talented members to help you grow a stronger business for fiercely reaching towards higher goals every day. We try to form an all-star team that deeply investigates your company culture to advertise about it.",
  },
  {
    id: 2,
    image: image2,
    title: "How to Fit into The Big Picture",
    text: "Our branding professionals have unique ways to avoid the well-worn path. They can get on a new original one for finding resolutions by imagining your company as a piece and study how to make it fit into the big picture.",
  },
  {
    id: 3,
    image: image3,
    title: "Build Enticing & Professional Website",
    text: "Putting together all of your business's data, rearrange and present in an appealing way to highlight your core values, services, and visions in the local area. Your online website would be a stepping stone for expanding company's visibility.",
  },
]);
</script>

<style scoped>
.mySwiper {
  width: 100%;
  height: 550px;
}

.text-card {
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0, 0, 0, 0.05), 0 0 60px rgba(150, 100, 255, 0.1) !important;
  background: white;
}
</style>
