<template>
  <div class="banner" id="home">
    <div class="parent">
      <v-container fluid>
        <v-row>
          <v-col cols="12" sm="10" md="8" lg="6">
            <div class="cont mt-16 pa-4 pa-md-8" data-aos="fade-up">
              <h3 class="text-h4 text-sm-h3 text-md-h2 mainTitle">
                {{ mainTitle }}
              </h3>
              <p class="text-body-1 text-sm-body-2 hint">{{ subTitle }}</p>
              <v-btn
                class="getDemo text-none mt-5 text-white"
                height="60"
                width="170"
                style="
                  background: linear-gradient(135deg, #5945e6 0%, #9c7af2 100%);
                  font-size: 16px;
                "
              >
                Get a Demo
              </v-btn>
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

<style scoped>
.banner .parent {
  min-height: 100vh; /* ارتفاع متجاوب */
  margin-top: 80px; /* توافق مع النافبار */
  background-image: url(../assets/mainSection.png);
  background-size: cover; /* الصورة تتكيف مع الحجم */
  background-repeat: no-repeat;
}

.banner .parent .cont {
  color: white;
}

.banner .parent .cont .mainTitle {
  color: #333;
  font-weight: 600;
  line-height: 1.2;
  font-size: 65px !important;
}

.banner .parent .cont .hint {
  margin: 30px 0;
  color: #696969;
  max-width: 650px;
  font-size: 20px !important;
  
}

.getDemo:hover {
  transform: translateY(-2px) !important;
  background: linear-gradient(100deg, #9c7af2 0%, #5945e6 100%) !important;
  box-shadow: 0 8px 25px rgba(156, 122, 242, 0.4) !important;
}

@media (max-width: 960px) {
  .banner .parent {
    min-height: 80vh;
    margin-top: 80px;
  }
}

@media (max-width: 600px) {
  .banner .parent {
    min-height: 60vh;
  }
}
@media (max-width: 848px) {
  .banner .parent {
    background-size: cover;
  }
}
</style>
