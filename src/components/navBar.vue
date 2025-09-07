<template>
  <v-app-bar :elevation="0" class="navbar" style="z-index: 999">
    <!-- Logo -->
    <div class="logo-section">
      <v-img :src="logo" alt="Logo" width="170"></v-img>
    </div>

    <!-- روابط Navbar للأجهزة الكبيرة -->
    <div class="nav-section" v-if="!isMobile">
      <v-list class="d-flex flex-row bg-transparent pa-0">
        <v-list-item
          v-for="item in items"
          :key="item.value"
          @click.prevent="scrollTo(item.id)"
          :title="item.title"
          :class="[
            'px-4 py-0 mx-2 custom-nav-item',
            { active: activeSection === item.id },
          ]"
          link
          hover
        ></v-list-item>
      </v-list>
    </div>

    <!-- أيقونة Hamburger للأجهزة الصغيرة -->
    <div class="actions-section">
      <!-- زر البحث / Drawer كما كان -->
      <v-icon
        style="color: #6d70a6"
        class="mr-3"
        size="30"
        @click="drawer = !drawer"
      >
        mdi-magnify
      </v-icon>

      <!-- زر Hire Us Now -->
      <v-btn
        v-if="!isMobile"
        class="hireNow text-none"
        style="color: #5945e6; font-size: 14px"
        variant="outlined"
        height="45"
        width="160"
      >
        Hire Us Now
      </v-btn>

      <!-- زر Hamburger يظهر فقط على شاشات صغيرة -->
      <v-icon
        v-if="isMobile"
        size="30"
        class="ml-3"
        @click="dropdownOpen = !dropdownOpen"
      >
        mdi-menu
      </v-icon>
    </div>
  </v-app-bar>

  <v-list
    v-if="isMobile && dropdownOpen"
    class="dropdown-nav"
    style="
      position: fixed;
      top: 80px;
      left: 0;
      width: 100%;
      background: white;
      z-index: 998;
    "
  >
    <v-list-item
      v-for="item in items"
      :key="item.value"
      @click.prevent="
        scrollTo(item.id);
        dropdownOpen = false;
      "
      class="px-4 py-2"
    >
      {{ item.title }}
    </v-list-item>
  </v-list>

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
        <v-img :src="logo" alt="Logo" width="170"></v-img>
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
import { ref, onMounted, onBeforeUnmount } from "vue";
import logo from "@/assets/logo.png"
let drawer = ref(false);
const dropdownOpen = ref(false);

const items = [
  { id: "home", title: "HOME", value: 1 },
  { id: "about", title: "ABOUT", value: 2 },
  { id: "requierment", title: "REQUIERMENT", value: 3 },
  { id: "pricing", title: "PRICING", value: 4 },
  { id: "partners", title: "PARTNERS", value: 5 },
];

const activeSection = ref("home");
const isMobile = ref(window.innerWidth < 1175);

const scrollTo = (id) => {
  const element = document.getElementById(id);
  if (element) {
    element.scrollIntoView({ behavior: "smooth" });
    activeSection.value = id;
  }
};

const handleScroll = () => {
  let current = null;
  items.forEach((item) => {
    const section = document.getElementById(item.id);
    if (section) {
      const rect = section.getBoundingClientRect();
      if (rect.top <= 150 && rect.bottom >= 150) {
        current = item.id;
      }
    }
  });
  if (current) activeSection.value = current;
};

const handleResize = () => {
  isMobile.value = window.innerWidth < 1175;
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
  window.addEventListener("resize", handleResize);
});

onBeforeUnmount(() => {
  window.removeEventListener("scroll", handleScroll);
  window.removeEventListener("resize", handleResize);
});
</script>

<style scoped>
.custom-nav-item :deep(.v-list-item-title) {
  font-weight: 500 !important;
  font-size: 16px !important;
  color: #7e7e7e !important;
}

.custom-nav-item.active :deep(.v-list-item-title) {
  color: #5945e6 !important;
  font-weight: bold !important;
  border-bottom: 2px solid #5945e6;
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
  height: 80px;
  padding: 10px 80px 10px 80px !important;
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

.dropdown-nav {
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
  transition: all 0.4s ease-in-out;
}

.dropdown-nav .v-list-item {
  border-bottom: 1px solid #eee;
  cursor: pointer;
}

@media (max-width: 1175px) {
  .navbar {
    padding: 10px 20px !important; /* تقليل الـ padding على الشاشات الصغيرة */
    justify-content: space-between !important; /* التأكد من توزيع العناصر */
  }

  .actions-section {
    margin-left: auto; /* دفع العناصر إلى أقصى اليمين */
    min-width: auto; /* إزالة الحد الأدنى للعرض */
    gap: 10px; /* تقليل المسافة بين زر الهامبرغر وأيقونة البحث */
  }

  .logo-section {
    margin-right: auto; /* التأكد من بقاء الشعار في اليسار */
  }
}
</style>
