<script setup>
import navBar from "./components/navBar.vue";
import mainSection from "./components/mainSection.vue";
import aboutSection from "./components/aboutSection.vue";
import analyticsSection from "./components/analyticsSection.vue";
import requirmentSection from "./components/requirmentSection.vue";
import carouselSection from "./components/carouselSection.vue";
import marketingSection from "./components/marketingSection.vue";
import pricingSection from "./components/pricingSection.vue";
import partnersSection from "./components/partnersSection.vue";
import contactsSection from "./components/contactsSection.vue";
import footerSection from "./components/footerSection.vue";
</script>

<template>
  <v-app>
    <navBar />
    <v-main class="pa-0">
      <mainSection />
      <aboutSection />
      <analyticsSection />
      <requirmentSection />
      <carouselSection />
      <marketingSection />
      <pricingSection />
      <partnersSection />
      <contactsSection />
      <footerSection />
    </v-main>
  </v-app>
</template>

<style scoped></style>
