<template>
  <q-layout view="lHh Lpr bFf">
    <q-page-container
      class="landing-content"
      :style="{ height: landingContentHeight }"
    >
      <div class="landing-content-inner">
        <Navigation />
        <router-view></router-view>
      </div>
    </q-page-container>

    <!-- Footer -->
    <FooterBar />
  </q-layout>
</template>

<script>
import { defineComponent, ref } from "vue";
import Navigation from "../components/NavigationBar.vue";
import FooterBar from "../components/FooterBar.vue";
export default defineComponent({
  name: "MainLayout",
  components: {
    Navigation, // Register Navigation component
    FooterBar,
  },
  setup() {
    const landingContentHeight = ref(
      window.innerWidth > 720 ? "697px" : "2028px"
    ); //

    window.addEventListener("resize", () => {
      landingContentHeight.value = window.innerWidth > 720 ? "926px" : "2028px";
    });
    return {
      landingContentHeight,
    };
  },
});
</script>

<style lang="scss" scoped>
.landing-content {
  position: relative;
  @media (min-width: 600px) {
    background-image: linear-gradient(
        to bottom,
        rgba(38, 194, 185, 0.5),
        rgba(40, 139, 231, 0.5)
      ),
      url("../assets/images/backgroundImage.png");
    background-size: cover;
  }
  @media (max-width: 599px) {
    background-image: linear-gradient(
        to bottom,
        rgba(40, 139, 231, 0.5),
        rgba(38, 194, 185, 0.5)
      ),
      url("../assets/images/backgroundImage.png");
    background-size: cover;
  } /* Path to your background image */
  background-position: center;
}

.landing-content-inner {
  max-width: 1200px;
  margin: 0px auto; /* Center align content */
  color: white;
}

.q-toolbar {
  background-color: #3498db; /* Blue background color for top bar */
}
</style>
