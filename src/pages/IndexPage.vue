<template>
  <q-page class="main-content">
    <div class="row main-row">
      <div class="col-12 col-md-6">
        <img
          v-if="$q.screen.gt.sm"
          src="../assets/images/indexImages/imageInBox.svg"
          alt=""
        />
        <img
          v-else
          src="../assets/images/indexImages/imageInBoxMobile.svg"
          alt=""
        />
        <p class="main-text">
          최고의 실력을 가진<br />
          외국인 인재를 찾고 계신가요?
        </p>
        <p class="sub-text">
          법률 및 인사관리 부담없이 <br v-if="$q.screen.gt.sm" />1주일 이내에
          원격으로 채용해보세요.
        </p>
        <p class="underlined-text" v-if="$q.screen.gt.sm">
          개발자가 필요하신가요?
        </p>
        <div class="row q-gutter" v-if="$q.screen.gt.sm">
          <div class="col-3">
            <hr class="horizontal-line" />
            <p class="description-text">월 120만원</p>
            <p class="detail-text">임금을 해당 국가를 기준으로 계산합니다.</p>
          </div>
          <div class="col-3 q-mx-lg">
            <hr class="horizontal-line" />
            <p class="description-text">평균 월 120만원</p>
            <p class="detail-text">임금을 해당 국가를 기준으로 계산합니다.</p>
          </div>
          <div class="col-3">
            <hr class="horizontal-line" />
            <p class="description-text">평균 월 120만원</p>
            <p class="detail-text">임금을 해당 국가를 기준으로 계산합니다.</p>
          </div>
        </div>
      </div>
      <div class="col-12 col-md-6"></div>
    </div>
    <div v-if="$q.screen.gt.sm" class="card-slider">
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
.main-row {
  @media (min-width: 601px) {
    padding-top: 60px;
  }
  @media (max-width: 600px) {
    padding: 20px;
  }
  @media (min-width: 601px) {
    margin-bottom: 80px;
    padding: 15px;
  }
}
.main-content {
  @media (max-width: 600px) {
    padding: 20px;
    padding-top: 40px;
  }
  @media (min-width: 601px) {
    padding-top: 60px;
  }
}
.main-text {
  @media (max-width: 600px) {
    font-size: 36px;
    font-weight: 900;
  }
  @media (min-width: 601px) {
    font-size: 48px;
    font-weight: 900;
  }
}
.sub-text {
  font-size: 24px;
  font-weight: 900;
  @media (max-width: 600px) {
    font-size: 18px;
    font-weight: 900;
  }
  @media (min-width: 601px) {
    font-size: 24px;
    font-weight: 900;
  }
}
.horizontal-line {
  margin-top: 50px;
  border-top: 0px;
}
.underlined-text {
  text-decoration: underline;
  font-weight: 900;
  font-size: 18px;
}
.description-text {
  margin-top: 15px;
  font-weight: 900;
  font-size: 18px;
}
.detail-text {
  margin-top: -10px;
  font-size: 16px;
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
