<template>
  <v-container
    data-aos="fade-up"
    style="padding: 100px 0"
    fluid
    class="contact d-flex flex-column align-center"
  >
    <v-row>
      <v-col cols="12">
        <h1 class="text">
          {{ mainText }}
        </h1>
      </v-col>
    </v-row>
    <v-row class="d-flex justify-center px-16">
      <v-col cols="12" lg="4" md="4" sm="12" class="d-flex justify-center"
        ><v-text-field
          type="text"
          bg-color="#5945e6;"
          width="350px"
          variant="outlined"
          placeholder="Your name"
        ></v-text-field
      ></v-col>
      <v-col cols="12" lg="4" md="4" sm="12" class="d-flex justify-center">
        <v-text-field
          type="email"
          bg-color="#5945e6;"
          width="350px"
          variant="outlined"
          placeholder="Email"
        ></v-text-field>
      </v-col>
      <v-col cols="12" lg="2" md="2" sm="12" class="d-flex justify-center">
        <v-btn
          class="submit text-none"
          style="color: #5945e6; font-size: 16px"
          height="55"
          width="170"
          >Submit</v-btn
        >
      </v-col>
    </v-row>
    <div class="mt-5">
      <p style="font-size: 18px; color: white; font-weight: 400">
        What’s next in AeroLand?
        <a href="#" style="text-decoration: none; color: #38cb89">Learn more</a>
      </p>
    </div>
  </v-container>
</template>

<script setup>
import { ref } from "vue";

const mainText = ref("493 businesses signed up last week. Join them!");
</script>
<style>
.contact {
  background: linear-gradient(
    -259deg,
    rgb(94, 96, 231),
    rgb(156, 122, 242) 65%
  );
}
.text {
  color: white;
  font-weight: 500;
  font-size: 40px;
  max-width: 500px;
  text-align: center;
}

.submit {
  transition: all 0.4s ease-in-out;
  background-color: white;
}
.submit:hover {
  color: white !important;
  transform: translateY(-4px) !important;
  color: black !important;
}
a {
  position: relative;
  text-decoration: none;
  color: white;
}

a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -2px;
  width: 0px !important;
  height: 3px;
  background-color: currentColor;
  transition: width 0.5s ease-in-out;
}

a:hover::after {
  width: 100% !important;
}
</style>
