<template>
  <v-container
  id="pricing"
  data-aos="fade-up"
    style="margin-top: 150px; background-color: #edf3fa"
    class="py-16"
    fluid
  >
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
    <v-row class="mt-10 px-16 ">
      <v-col cols="12" lg="3" md="4" sm="6" v-for="card in cards" :key="card.id" >
        <v-card class="priceCard d-flex flex-column align-center pa-10">
          <v-img :src="card.icon" style="width: 19%"></v-img>
          <v-card-title class="mt-3" style="font-size: 25px">{{
            card.title
          }}</v-card-title>
          <div class="price-display">
            <span class="price-value">{{ card.price }}</span>
            <span class="mo-text">/mo</span>
          </div>
          <p style="color: #7e7e7e" class="mt-4">{{ card.subtitle }}</p>
          <p
            style="
              text-align: center;
              line-height: 1.6rem;
              color: #7e7e7e;
              font-size: 14px;
            "
            class="mt-3"
          >
            {{ card.text }}
          </p>
          <v-btn
            class="getStarted text-none mt-8"
            style="color: #5945e6; font-size: 14px"
            variant="outlined"
            height="45"
            width="170"
            >Get Started</v-btn
          >
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script setup>
import { ref } from "vue";
import card1 from "../assets/card1.png";
import card2 from "../assets/card2.png";
import card3 from "../assets/card3.png";
import card4 from "../assets/card4.png";

const mainTitle = ref("Affordable for everyone!");
const subTitle = ref(
  "If you are planning on developing a product landing app or website, take a look at this beautiful-crafted and error-free HTML template"
);

const cards = ref([
  {
    id: 1,
    icon: card1,
    title: "Free",
    price: "0",
    subtitle: "03 projects",
    text: "Power And Predictive Dialing Quality & Customer ExperienceTry for free, forever!",
  },
  {
    id: 2,
    icon: card2,
    title: "Personal",
    price: "19",
    subtitle: "03 projects",
    text: "Power And Predictive Dialing Quality & Customer Experience 24/7 phone and email support",
  },
  {
    id: 3,
    icon: card3,
    title: "Group",
    price: "29",
    subtitle: "50 projects",
    text: "Power And Predictive Dialing Quality & Customer ExperienceTry for free, forever!",
  },
  {
    id: 4,
    icon: card4,
    title: "Enterprise",
    price: "49",
    subtitle: "Unlimited projects",
    text: "Power And Predictive Dialing Quality & Customer ExperienceTry for free, forever!",
  },
]);
</script>
<style>
.price-display {
  display: flex;
  align-items: baseline;
  justify-content: center;
}

.price-value {
  font-size: 3rem;
  font-weight: normal;
  color: #333;
  position: relative;
}

.price-value::before {
  content: "$";
  font-size: medium;
  position: absolute;
  right: 55px;
  bottom: 40px;
  color: #999;
}
.mo-text {
  font-size: 1rem;
  color: #999;
  margin-left: 4px;
}
.getStarted {
  transition: all 0.4s ease-in-out !important;
}
.getStarted:hover {
  background: linear-gradient(135deg, #5945e6 0%, #9c7af2 100%) !important;
  color: white !important;
}

.priceCard {
  transition: all 0.3s ease-in-out !important;
  height: 500px !important;
}

.priceCard:hover {
  transform: translateY(-4px) !important;
  box-shadow: 0 0px 20px rgba(0, 0, 0, 0.05), 0 0 60px rgba(150, 100, 255, 0.1) !important;
}
</style>
