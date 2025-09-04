<template>
  <div class="banner">
    <div class="parent">
      <v-container fluid>
        <v-row>
          <v-col cols="6">
            <div class="cont mt-16 pl-8">
              <h3>{{ mainTitle }}</h3>
              <p class="hint">
                {{ subTitle }}
              </p>
              <v-btn
                class="getDemo text-none mt-5 text-white"
                height="50"
                width="150"
                style="
                  background: linear-gradient(135deg, #5945e6 0%, #9c7af2 100%);
                "
                >Get a Demo</v-btn
              >
            </div>
          </v-col>
        </v-row>
      </v-container>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const mainTitle = ref("Executive branding campaign");
const subTitle = ref(
  "True branding starts from within. We create and adopt unique branding resolution to strengthen your business."
);
</script>
<style>
.banner .parent {
  height: 600px;
  margin-top: 100px;
  background-image: url(../assets/mainSection.png);
  background-size: cover;
  background-position: left top;
}

.banner .parent .cont {
  color: white;
  padding: 40px 0 0 70px;
}

.banner .parent .cont h3 {
  color: #333;
  font-size: 55px;
  font-weight: 500;
  line-height: 1.2;
}

.banner .parent .cont .hint {
  margin: 20px 0;
  color: #696969;
  font-size: 18px;
  max-width: 570px;
}

.getDemo:hover {
  transform: translateY(-2px) !important;
  background: linear-gradient(100deg, #9c7af2 0%, #5945e6 100%) !important;
  box-shadow: 0 8px 25px rgba(156, 122, 242, 0.4) !important;
}
</style>
