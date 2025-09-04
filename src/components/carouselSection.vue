<template>
  <v-container fluid class="pt-15">
    <swiper
      :slides-per-view="1"
      :space-between="30"
      :loop="true"
      :pagination="{ clickable: true }"
      :autoplay="{ delay: 3000, disableOnInteraction: false }"
      class="mySwiper"
    >
      <swiper-slide v-for="item in items" :key="item.id">
        <div class="slide-content">
          <v-row class="d-flex align-center">
            <v-col cols="6">
              <v-img :src="item.image" style="width: 600px"></v-img>
            </v-col>
            <v-col cols="6" style="max-width: 550px">
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
  <v-container>
    <v-row class="px-16">
      <v-col cols="6" class="d-flex col1">
        <v-progress-circular
          color="#ffd54f"
          :size="150"
          :model-value="value1"
          :rotate="360"
        >
          <div
            style="
              display: flex;
              justify-content: center;
              align-items: center;
              background: linear-gradient(135deg, #ffd54f, #ff7043);
              color: white;
              width: 130px;
              height: 130px;
              border-radius: 50%;
            "
          >
            <p class="font-weight-medium" style="font-size: 30px">
              {{ value1 }}
            </p>
          </div></v-progress-circular
        >
        <v-card class="ml-10" variant="0">
          <p
            v-for="item in listItems1"
            :key="item.id"
            :class="{ 'first-item': item.id === 1 }"
            style="line-height: 2.2rem; color: #7e7e7e; font-size: 15px"
          >
            {{ item.text }}
          </p>
        </v-card>
      </v-col>
      <v-col cols="6" class="d-flex col2">
        <v-progress-circular
          color="rgb(89, 69, 230)"
          :size="150"
          :model-value="value2"
          :rotate="360"
        >
          <div
            style="
              display: flex;
              justify-content: center;
              align-items: center;
              background: linear-gradient(
                135deg,
                rgb(89, 69, 230),
                rgb(156, 122, 242)
              );
              color: white;
              width: 130px;
              height: 130px;
              border-radius: 50%;
            "
          >
            <p class="font-weight-medium" style="font-size: 30px">
              {{ value2 }}
            </p>
          </div></v-progress-circular
        >
        <v-card class="ml-10" variant="0">
          <p
            v-for="item in listItems1"
            :key="item.id"
            :class="{ 'first-item': item.id === 1 }"
            style="line-height: 2.2rem; color: #7e7e7e; font-size: 15px"
          >
            {{ item.text }}
          </p>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { ref } from "vue";
import image1 from "../assets/swiperImage1.png";
import image2 from "../assets/swiperImage2.png";
import image3 from "../assets/swiperImage3.png";
import { onBeforeUnmount, onMounted } from "vue";

const value1 = ref(0);
const value2 = ref(0);

let interval1 = -1;
let interval2 = -1;
onMounted(() => {
  interval1 = setInterval(() => {
    if (value1.value === 80) {
      return (value1.value = 80);
    }
    value1.value += 1;
  }, 50);

  interval2 = setInterval(() => {
    if (value2.value === 75) {
      return (value2.value = 75);
    }
    value2.value += 1;
  }, 50);
});
onBeforeUnmount(() => {
  clearInterval(interval1);
  clearInterval(interval2);
});

// تعريف البيانات
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

const listItems1 = ref([
  {
    id: 1,
    text: "Digital Marketing",
  },
  {
    id: 2,
    text: "Keyword rank tracking",
  },
  {
    id: 3,
    text: "Website audit",
  },
  {
    id: 4,
    text: "Marketing, SEO",
  },
  {
    id: 5,
    text: "Social Media",
  },
  {
    id: 6,
    text: "Social Media",
  },
  {
    id: 7,
    text: "On-page SEO Audit",
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

.first-item {
  color: #2e3280 !important;
  font-weight: 600;
  font-size: 17px !important;
  margin-bottom: 7px !important;
}
.col1 {
  position: relative;
}
.col1::before {
  content: "";
  width: 45px;
  height: 45px;
  border-radius: 50%;
  background: linear-gradient(135deg, #ff7043, #ffd54f);
  position: absolute;
  left: 10px;
  top: 110px;
  z-index: 1;
  animation: floatY 1.6s ease-in-out infinite alternate;
}
.col1::after {
  content: "";
  width: 15px;
  height: 15px;
  border-radius: 50%;
  background: linear-gradient(135deg, #ff7043, #ffd54f);
  position: absolute;
  left: 165px;
  top: 90px;
  z-index: 1;
  animation: floatY 1.6s ease-in-out infinite alternate;
}
.col2 {
  position: relative;
}
.col2::before {
  content: "";
  width: 45px;
  height: 45px;
  border-radius: 50%;
  background: linear-gradient(
    135deg,
    rgb(89, 69, 230) 0%,
    rgb(156, 122, 242) 100%
  );
  position: absolute;
  left: 10px;
  top: 110px;
  z-index: 1;
  animation: floatY 1.6s ease-in-out infinite alternate;
}
.col2::after {
  content: "";
  width: 15px;
  height: 15px;
  border-radius: 50%;
  background: linear-gradient(
    135deg,
    rgb(89, 69, 230) 0%,
    rgb(156, 122, 242) 100%
  );
  position: absolute;
  left: 165px;
  top: 90px;
  z-index: 1;
  animation: floatY 1.5s ease-in-out infinite alternate;
}

@keyframes floatY {
  from {
    transform: translateY(0);
  }
  to {
    transform: translateY(-20px);
  }
}
</style>
