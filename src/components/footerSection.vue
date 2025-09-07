<template>
  <v-container class="pt-16" data-aos="fade-up">
    <v-row>
      <v-col cols="12" lg="3" md="6" sm="12">
        <v-img :src="logo" style="width: 210px"></v-img>
        <v-list style="font-size: 15px; color: #7e7e7e">
          <v-list-item>Your address goes here</v-list-item>
          <v-list-item class="hoverItem">demo@example.com</v-list-item>
          <v-list-item class="hoverItem">0123456789</v-list-item>
          <v-list-item class="hoverItem4">www.example.com</v-list-item>
        </v-list>
      </v-col>
      <v-col cols="12" lg="3" md="6" sm="12">
        <v-list-item style="font-size: 20px; font-weight: 500"
          >Who we are</v-list-item
        >
        <v-list style="font-size: 15px; color: #7e7e7e">
          <v-list-item class="hoverItem">About us</v-list-item>
          <v-list-item class="hoverItem">Before you go</v-list-item>
          <v-list-item class="hoverItem">Online check in</v-list-item>
          <v-list-item class="hoverItem">FAQ</v-list-item>
        </v-list>
      </v-col>
      <v-col cols="12" lg="3" md="6" sm="12">
        <v-list-item style="font-size: 20px; font-weight: 500"
          >Quick links</v-list-item
        >
        <v-list style="font-size: 15px; color: #7e7e7e">
          <v-list-item class="hoverItem">Pick up locations</v-list-item>
          <v-list-item class="hoverItem">Terms of Payment</v-list-item>
          <v-list-item class="hoverItem">Privacy Policy</v-list-item>
          <v-list-item class="hoverItem">Where to Find Us</v-list-item>
        </v-list>
      </v-col>
      <v-col cols="12" lg="3" md="6" sm="12">
        <v-card
          class="pa-5"
          style="font-size: 14px; background-color: #5945e60d"
        >
          <p style="color: #7e7e7e" class="mb-1">
            "The ocean never ceases to amaze!" Feature: Ben Klea
          </p>
          <div class="links" style="display: flex; flex-direction: column">
            <a href="#" style="color: #38cb89">https://t.co/jSRMsZAdPW</a>
            <a href="#" style="color: #38cb89">https://t.co/2iDReuyPMt</a>
          </div>
        </v-card>
        <v-card class="pt-5 pl-6" variant="0">
          <v-row>
            <v-col cols="1">
              <v-icon color="#5e60e7" size="20">mdi-twitter</v-icon>
            </v-col>
            <v-col cols="6">
              <p style="font-size: 14px; font-weight: 500">Unsplash</p>
              <p style="color: #7e7e7e; font-size: 14px">May 07, 2023</p>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>

    <v-divider class="mt-16 mb-7"></v-divider>
    <v-card variant="0" class="ma-10">
      <v-row class="justify-center">
        <v-col
          cols="12"
          lg="10"
          md="12"
          sm="12"
          class="text-center text-lg-start"
        >
          <div
            class="d-flex flex-wrap align-center justify-center justify-lg-start"
            style="font-size: 15px; color: #7e7e7e; gap: 3px"
          >
            <span>&copy; {{ year }}</span>
            <span style="font-weight: 600">AeroLand</span>
            <span>Made with ❤ by</span>
            <span style="font-weight: 600">HasThemes</span>
          </div>
        </v-col>
        <v-col cols="12" lg="2" md="12" sm="12" class="text-center text-lg-end">
          <div class="d-flex justify-center justify-lg-end">
            <a href="#" class="link"
              ><v-icon class="icon facebook">mdi mdi-facebook</v-icon></a
            >
            <a href="#" class="link"
              ><v-icon class="icon twitter">mdi mdi-twitter</v-icon></a
            >
            <a href="#" class="link"
              ><v-icon class="icon instagram">mdi mdi-instagram</v-icon></a
            >
          </div>
        </v-col>
      </v-row>
    </v-card>
  </v-container>
</template>
<script setup>
import { ref } from "vue";
import logo from "@/assets/logo.png";

const year = ref(new Date().getFullYear());
</script>

<style>
.hoverItem {
  position: relative !important;
  cursor: pointer;
}
.hoverItem::before {
  content: "";
  position: absolute !important;
  left: 15px;
  bottom: 10px;
  width: 0px !important;
  height: 1px;
  background-color: #5e60e7;
  transition: width 0.5s ease-in-out;
}

.hoverItem:hover::before {
  width: 60% !important;
}

.hoverItem:hover {
  color: #5e60e7;
}
.hoverItem4 {
  position: relative !important;
  cursor: pointer;
  color: #38cb89 !important;
}
.hoverItem4::before {
  content: "";
  position: absolute !important;
  left: 15px;
  bottom: 10px;
  width: 0px !important;
  height: 1px;
  background-color: #38cb89;
  transition: width 0.5s ease-in-out;
}

.hoverItem4:hover::before {
  width: 50% !important;
}

.link {
  padding: 10px;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 20px;
}

.facebook {
  transition: all 0.2s ease-in-out;
  color: #7e7e7e;
}
.facebook:hover {
  color: #1877f2 !important;
  transform: scale(1.2);
}
.instagram {
  transition: all 0.2s ease-in-out;
  color: #7e7e7e;
}
.instagram:hover {
  background: linear-gradient(
    45deg,
    #405de6,
    #5851db,
    #833ab4,
    #c13584,
    #e1306c,
    #fd1d1d,
    #f56040,
    #f77737,
    #fcaf45,
    #ffdc80
  );
  -webkit-background-clip: text; /* لتطبيق التدرج على النص */
  color: transparent; /* لجعل النص شفافًا بحيث يظهر التدرج */
  transform: scale(1.2); /* التكبير عند التمرير */
}
.twitter {
  transition: all 0.2s ease-in-out;
  color: #7e7e7e;
}
.twitter:hover {
  color: #1da1f2 !important;
  transform: scale(1.2);
}
</style>
