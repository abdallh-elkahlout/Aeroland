<template>
  <v-container class="pt-10">
    <v-row class="px-16">
      <!-- العمود الأول -->
      <v-col cols="12" lg="6" md="6" sm="12" class="col1 d-flex justify-center align-center">
        <div class="d-flex flex-column flex-sm-row align-center">
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
            </div>
          </v-progress-circular>

          <v-card class="ml-sm-10 mt-5 mt-sm-0" variant="0">
            <p
              v-for="item in listItems1"
              :key="item.id"
              :class="{ 'first-item': item.id === 1 }"
              style="line-height: 2.2rem; color: #7e7e7e; font-size: 15px"
            >
              {{ item.text }}
            </p>
          </v-card>
        </div>
      </v-col>

      <!-- العمود الثاني -->
      <v-col cols="12" lg="6" md="6" sm="12" class="col2 d-flex justify-center align-center">
        <div class="d-flex flex-column flex-sm-row align-center">
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
            </div>
          </v-progress-circular>

          <v-card class="ml-sm-10 mt-5 mt-sm-0" variant="0">
            <p
              v-for="item in listItems1"
              :key="item.id"
              :class="{ 'first-item': item.id === 1 }"
              style="line-height: 2.2rem; color: #7e7e7e; font-size: 15px"
            >
              {{ item.text }}
            </p>
          </v-card>
        </div>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref, onBeforeUnmount, onMounted } from "vue";

const value1 = ref(0);
const value2 = ref(0);

let interval1 = -1;
let interval2 = -1;

onMounted(() => {
  interval1 = setInterval(() => {
    if (value1.value === 80) return;
    value1.value += 1;
  }, 50);

  interval2 = setInterval(() => {
    if (value2.value === 75) return;
    value2.value += 1;
  }, 50);
});

onBeforeUnmount(() => {
  clearInterval(interval1);
  clearInterval(interval2);
});

const listItems1 = ref([
  { id: 1, text: "Digital Marketing" },
  { id: 2, text: "Keyword rank tracking" },
  { id: 3, text: "Website audit" },
  { id: 4, text: "Marketing, SEO" },
  { id: 5, text: "Social Media" },
  { id: 6, text: "Social Media" },
  { id: 7, text: "On-page SEO Audit" },
]);
</script>

<style>
.first-item {
  color: #2e3280 !important;
  font-weight: 600;
  font-size: 17px !important;
  margin-bottom: 7px !important;
}
.col1,
.col2 {
  position: relative;
}

/* دوائر متحركة العمود الأول */
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

/* دوائر متحركة العمود الثاني */
.col2::before {
  content: "";
  width: 45px;
  height: 45px;
  border-radius: 50%;
  background: linear-gradient(135deg, rgb(89, 69, 230), rgb(156, 122, 242));
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
  background: linear-gradient(135deg, rgb(89, 69, 230), rgb(156, 122, 242));
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
