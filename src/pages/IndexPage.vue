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
      <div class="col-12 col-md-6">
        <div class="flex justify-center">
          <img
            src="../assets/images/indexImages/indexCardDescription.svg"
            alt=""
          />
        </div>
        <div class="flex justify-between card-set-container">
          <div class="flex items-center">
            <q-icon
              @click="changeActiveIndex(1)"
              size="lg"
              name="chevron_left"
            ></q-icon>
          </div>
          <div class="carousel-container">
            <q-card class="carousel-card card1">
              <div class="flex justify-center image-container">
                <img src="../assets/images/indexImages/photograph.png" alt="" />
              </div>
              <p class="talent-name text-center">Abhishek Gupta</p>
              <p class="talent-experience text-center">마케팅 · 2y+</p>
              <div class="flex justify-center">
                <p class="qualities">마케팅 콘텐츠 제작</p>
              </div>
              <div class="flex justify-center">
                <p class="qualities">인스타그램 관리</p>
              </div>
              <div class="flex justify-center">
                <p class="qualities">트위터 관리</p>
                <p class="qualities">블로그 글 작성</p>
              </div>
            </q-card>
            <q-card class="carousel-card card2">
              <div class="flex justify-center image-container">
                <img src="../assets/images/indexImages/photograph.png" alt="" />
              </div>
              <p class="talent-name text-center">Abhishek Gupta</p>
              <p class="talent-experience text-center">마케팅 · 2y+</p>
              <div class="flex justify-center">
                <p class="qualities">마케팅 콘텐츠 제작</p>
              </div>
              <div class="flex justify-center">
                <p class="qualities">인스타그램 관리</p>
              </div>
              <div class="flex justify-center">
                <p class="qualities">트위터 관리</p>
                <p class="qualities">블로그 글 작성</p>
              </div>
            </q-card>
            <q-card class="carousel-card card3">
              <div class="flex justify-center image-container">
                <img src="../assets/images/indexImages/photograph.png" alt="" />
              </div>
              <p class="talent-name text-center">Abhishek Gupta</p>
              <p class="talent-experience text-center">마케팅 · 2y+</p>
              <div class="flex justify-center">
                <p class="qualities">마케팅 콘텐츠 제작</p>
              </div>
              <div class="flex justify-center">
                <p class="qualities">인스타그램 관리</p>
              </div>
              <div class="flex justify-center">
                <p class="qualities">트위터 관리</p>
                <p class="qualities">블로그 글 작성</p>
              </div>
            </q-card>
          </div>

          <div class="flex items-center">
            <q-icon size="lg" name="chevron_right"></q-icon>
          </div>
        </div>
        <div v-if="$q.screen.lt.sm" class="checkbox-container">
          <div class="flex" v-if="$q.screen.lt.sm">
            <div class="flex one-checkbox">
              <img src="../assets/images/Checkbox.svg" alt="" />
              <p>한국어 능력</p>
            </div>
            <div class="flex one-checkbox">
              <img src="../assets/images/Checkbox.svg" alt="" />
              <p>업무 수행 능력</p>
            </div>
          </div>
          <div class="flex" v-if="$q.screen.lt.sm">
            <div class="flex items-center one-checkbox">
              <img src="../assets/images/Checkbox.svg" alt="" />
              <p>한국어 능력</p>
            </div>
            <div class="flex items-center one-checkbox">
              <img src="../assets/images/Checkbox.svg" alt="" />
              <p>업무 수행 능력</p>
            </div>
          </div>
        </div>
        <p class="yellow-text" v-if="$q.screen.lt.sm">발자가 필요하신가요?</p>
      </div>
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
  @media (min-width: 601px) {
    margin-bottom: 40px;
  }
}
.card-set-container {
  @media (max-width: 600px) {
    margin-top: 20px;
  }

  height: 100%;
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

.carousel-container {
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}

.carousel-card {
  @media (max-width: 600px) {
    width: 215.41px;
    height: 287px;
  }

  @media (min-width: 601px) {
    width: 259px;
    height: 366px;
  }
  border-radius: 12px;
  transition: transform 0.5s ease-in-out, opacity 0.5s ease-in-out;
  .image-container img {
    width: 120px;
    height: 120px;
    margin-top: 40px;
    @media (max-width: 600px) {
      width: 80px;
      height: 80px;
      margin-top: 20px;
    }
  }
  .talent-name {
    color: #24252f;
    font-size: 24px;
    font-weight: 900;
    margin-top: 20px;
    @media (max-width: 600px) {
      font-size: 18px;
      font-weight: 900;
      margin-top: 10px;
    }
  }
  .talent-experience {
    color: #4a77ff;
    font-size: 16px;
    font-weight: 900;
    margin-top: -15px;
    @media (max-width: 600px) {
      font-size: 14px;
      font-weight: 900;
      margin-top: -10px;
    }
  }
  .qualities {
    color: #5e626f;
    border: 1.4px solid #c1c5cf;
    border-radius: 6px;
    padding: 4px 6px;
    font-weight: 900;
    font-size: 16px;
    max-width: 132px;
    margin: 4px 2px;
    @media (max-width: 600px) {
      font-size: 12px;
      font-weight: 900;
    }
  }
}

.card1 {
  background-color: rgba(237, 252, 255, 1);
  position: absolute;
  left: -20px;
  @media (max-width: 600px) {
    left: -80px;
  }
  @media (min-width: 601px) {
    width: 259px;
    height: 366px;
  }
  .image-container img {
    width: 90px;
    height: 90px;
    margin-top: 40px;
    @media (max-width: 600px) {
      width: 40px;
      height: 40px;
      margin-top: 20px;
    }
  }
}

.card2 {
  background-color: rgba(237, 252, 255, 1);
  position: absolute;
  right: -10px;
  @media (max-width: 600px) {
    right: -80px;
  }
  .image-container img {
    width: 90px;
    height: 90px;
    margin-top: 40px;
    @media (max-width: 600px) {
      width: 40px;
      height: 40px;
      margin-top: 20px;
    }
  }
}

.card3 {
  background-color: white;
  position: absolute;
  width: 292px;
  height: 408px;
  @media (max-width: 600px) {
    width: 200.41px;
    height: 307px;
  }
}
.checkbox-container {
  margin-top: 30px;
  .one-checkbox {
    margin-left: 13px;
    padding-top: 4px;
    p {
      font-size: 16px;
      font-weight: 900;
      margin-top: 12px;
      margin-left: 4px;
    }
  }
}
.yellow-text {
  color: #fbff23;
  font-size: 16px;
  font-weight: 900;
  margin-top: 12px;
  margin-left: 12px;
  text-decoration: underline;
}
</style>
