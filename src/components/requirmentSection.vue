<template>
  <v-container class="mt-16 container px-5 pb-1" fluid>
    <v-row class="mt-16">
      <v-col cols="6">
        <div class="content" style="padding-left: 140px">
          <h1
            style="font-size: 50px; color: #2e3280; line-height: 4rem"
            class="font-weight-medium mb-5"
          >
            {{ mainTitle }}
          </h1>
          <p
            style="font-size: 15px; color: dimgray; max-width: 350px"
            class="font-weight-thin"
          >
            {{ subTitle }}
          </p>
          <v-list style="background-color: transparent">
            <v-list-item
              class="ml-0"
              style="color: #7e7e7e; font-size: 15px"
              v-for="check in checks"
              :key="check.id"
              prepend-icon="mdi-check"
              >{{ check.text }}</v-list-item
            >
          </v-list>
          <v-btn
            class="getDemo text-none mt-8 text-white"
            height="50"
            width="150"
            style="
              background: linear-gradient(135deg, #5945e6 0%, #9c7af2 100%);
            "
            >Learn More</v-btn
          >
        </div>
      </v-col>
      <v-col cols="6" style="position: relative;">
        <v-img :src="image" style="bottom: 130px"></v-img>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from "vue";
import image from "../assets/requirments.png";

const mainTitle = ref("Meeting all of your requirements for SEO");
const subTitle = ref(
  "AeroLand creates a prominent advantage for your business with strong features."
);

const checks = ref([
  {
    id: 1,
    text: "Customer First Content-focused Displaying Effects",
  },
  {
    id: 2,
    text: "High Definition Full-screen Sliders & Backgrounds",
  },
  {
    id: 3,
    text: "Fast Loading, Reader Friendly Navigation Style",
  },
]);
</script>
<style>
.container {
  background-color: rgb(237, 243, 250);
}
</style>
