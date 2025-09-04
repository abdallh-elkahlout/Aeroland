<template>
  <v-app-bar :elevation="0" class="pa-7 px-13 navbar" style="z-index: 999">
    <div class="logo-section">
      <v-img src="/src/assets/logo.png" alt="Logo" width="170"></v-img>
    </div>

    <div class="nav-section">
      <v-list class="d-flex flex-row bg-transparent pa-0">
        <v-list-item
          v-for="item in items"
          :key="item.value"
          :title="item.title"
          class="px-4 py-0 mx-2 custom-nav-item"
          link
          hover
        ></v-list-item>
      </v-list>
    </div>

    <div class="actions-section">
      <v-icon
        style="color: #6d70a6"
        class="mr-3"
        size="30"
        @click="drawer = !drawer"
      >
        mdi-magnify
      </v-icon>
      <v-btn
        class="hireNow text-none"
        style="color: #5945e6; font-size: 14px"
        variant="outlined"
        height="55"
        width="160"
        >Hire Us Now</v-btn
      >
    </div>
  </v-app-bar>

  <v-navigation-drawer
    v-model="drawer"
    permanent
    class="floating-drawer"
    overlay
    temporary
    location="left"
    width="400"
    style="
      position: fixed;
      top: 0;
      left: 0;
      height: 100vh;
      z-index: 1000;
      background: linear-gradient(135deg, #5945e6 0%, #9c7af2 100%) !important;
    "
  >
    <div
      class="logo pt-5 pl-3 bg-white pa-4"
      style="height: 75px; display: flex; justify-content: space-between"
    >
      <div class="image" style="cursor: pointer">
        <v-img src="/src/assets/logo.png" alt="Logo" width="170"></v-img>
      </div>
      <v-icon size="35" @click="drawer = false">mdi-close</v-icon>
    </div>
    <div class="search mt-5 pa-7">
      <form action="">
        <v-text-field
          class="text-white"
          color="white"
          variant="underlined"
          placeholder="Enter Search Keyword..."
          bg-color="transparent"
          append-inner-icon="mdi-magnify"
        ></v-text-field>
      </form>
    </div>
  </v-navigation-drawer>
</template>

<script setup>
import { ref } from "vue";
let drawer = ref(false);
const items = [
  {
    title: "HOME",
    value: 1,
  },
  {
    title: "ABOUT",
    value: 2,
  },
  {
    title: "REQUIERMENT",
    value: 3,
  },
  {
    title: "PRICING",
    value: 4,
  },
  {
    title: "PARTNERS",
    value: 5,
  },
];
</script>

<style scoped>
.custom-nav-item :deep(.v-list-item-title) {
  font-weight: 500 !important;
  font-size: 16px !important;
  color: #7e7e7e !important;
  font-size: 15px !important;
}
.hireNow {
  transition: all 0.4s ease-in-out;
}
.hireNow:hover {
  background: linear-gradient(135deg, #5945e6 0%, #9c7af2 100%) !important;
  color: white !important;
}

.navbar {
  display: flex !important;
  justify-content: space-between !important;
  align-items: center !important;
  width: 100% !important;
}

.logo-section {
  flex: 0 0 auto;
  min-width: 170px;
}

.nav-section {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.actions-section {
  flex: 0 0 auto;
  display: flex;
  align-items: center;
  gap: 20px;
  min-width: 200px;
}
</style>
