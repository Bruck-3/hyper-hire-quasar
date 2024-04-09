<template>
  <q-page class="main-content">
    <div class="card-slider">
      <div class="card-wrapper flex">
        <q-card
          flat
          class="features-card"
          :style="{ transform: `translateX(${translateX}px)` }"
          v-for="(feature, index) in infiniteFeatures"
          :key="index"
        >
          <img :src="feature.src" alt="" />
          <q-card-section>
            {{ feature.name }}
          </q-card-section>
        </q-card>
      </div>
    </div>
  </q-page>
</template>

<script>
import desktop1 from "../assets/images/indexImages/desktop1.svg";
import desktop2 from "../assets/images/indexImages/desktop2.svg";
import desktop3 from "../assets/images/indexImages/desktop3.svg";
import desktop4 from "../assets/images/indexImages/desktop4.svg";
import desktop5 from "../assets/images/indexImages/desktop5.svg";
import { defineComponent, ref } from "vue";
const features = [
  {
    src: desktop1,
    name: "해외 마케팅",
  },
  {
    src: desktop2,
    name: "퍼블리셔",
  },
  {
    src: desktop3,
    name: "캐드원(제도사)",
  },
  {
    src: desktop4,
    name: "해외 세일즈",
  },
  {
    src: desktop5,
    name: "해외 CS",
  },
];
export default defineComponent({
  name: "IndexPage",
  setup() {
    const currentIndex = ref(0);
    const translateX = ref(0);

    // Duplicate features to create infinite loop
    const infiniteFeatures = ref([]);

    // Function to initialize infiniteFeatures
    const initInfiniteFeatures = () => {
      infiniteFeatures.value = [
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
        ...features,
      ];
    };

    initInfiniteFeatures();

    const startSlider = () => {
      setInterval(() => {
        currentIndex.value = (currentIndex.value + 1) % features.length;
        translateX.value -= 340;
        // if (currentIndex.value === 0) {
        //   translateX.value = 0;
        // }
      }, 5000);
    };

    startSlider();

    return {
      features,
      translateX,
      infiniteFeatures,
    };
  },
});
</script>

<style lang="scss" scoped>
.main-content {
  @media (max-width: 600px) {
    padding: 20px;
    padding-top: 40px;
  }
  @media (min-width: 601px) {
    padding-top: 60px;
  }
}
.card-slider {
  width: 100%;
}
.card-wrapper {
  width: 100%;
  flex-wrap: nowrap;
  overflow-x: hidden;
}
.features-card {
  min-width: 332px !important;
  height: 88px;
  transition: transform 1s ease-in-out;
  background: rgba(255, 255, 255, 0.2);
  color: white;
  border-radius: 8px;
  margin-right: 8px;
  display: flex;
  align-items: center;
  padding: 0px 20px;
  img {
    width: 56px;
    height: 56px;
  }
  font-size: 24px;
  font-weight: bold;
}
</style>
