<template>
  <q-footer class="footer">
    <div class="remove-fixed-bottom">
      <div class="row">
        <div class="col-12 col-md-4">
          <img src="../assets/images/footerLogo.svg" alt="" />
          <p class="text-subtitle1">
            우리는 국가의 장벽을 넘어 최고의 인재를 매<br />칭해드립니다.
          </p>
          <p class="text-weight-bold detail-text">010-0000-0000</p>
          <p class="text-weight-bold detail-text">aaaaa@naver.com</p>
        </div>
        <div class="col-12 col-md-8">
          <div class="row cards-row">
            <div
              v-for="(item, index) in footerDetails"
              :key="index"
              class="col-6 col-md-3"
            >
              <q-card flat rounded-borders class="my-card">
                <q-card-section>
                  <img :src="item.src" alt="" />
                </q-card-section>

                <p class="detail-text-for text-weight-bold text-subtitle2">
                  {{ item.name }}
                </p>
                <div
                  class="flex align-center items-start cursor-pointer click-div"
                >
                  <p class="detail-text-for text-weight-bold">바로가기</p>
                  <img :src="arrowRight" class="q-ml-sm" />
                </div>
              </q-card>
            </div>
          </div>
        </div>
      </div>
      <div class="row" :class="$q.screen.lt.sm ? 'q-mt-md' : 'q-mt-xl'">
        <div class="col-12 col-md-4">
          <div class="row" :class="$q.screen.lt.sm ? 'q-mt-md' : ''">
            <div class="col-6">
              <p class="text-subtitle2 detail-text">상호명</p>
              <p class="detail-text">하이퍼하이어</p>
              <p class="text-weight-bold detail-text">
                Hyperhire India Private Limited
              </p>
            </div>
            <div class="col-6 q-pl-md">
              <p class="text-subtitle2 detail-text text-weight-bold">
                대표 CEO
              </p>
              <p class="detail-text">김주현</p>
              <p class="text-weight-bold detail-text">Juhyun Kim</p>
            </div>
          </div>
        </div>
        <div class="col-12 col-md-8">
          <div class="row cards-row">
            <div class="row" :class="$q.screen.lt.sm ? 'q-mt-md' : ''">
              <div class="col-12 col-md-3">
                <p class="text-subtitle2 detail-text text-weight-bold">
                  사업자등록번호 CIN
                </p>
                <p class="detail-text text-weight-bold">427-86-01187</p>
                <p class="text-weight-bold detail-text">
                  U74110DL2016PTC290812
                </p>
              </div>
              <div
                class="col-12 col-md-8"
                :class="$q.screen.lt.sm ? 'q-mt-md' : 'q-ml-lg'"
              >
                <p class="text-subtitle2 detail-text text-weight-bold">
                  주소 ADDRESS
                </p>
                <p class="detail-text text-weight-bold">
                  서울특별시 강남대로 479, 지하 1층 238호
                </p>
                <p class="text-weight-bold detail-text">
                  D-138, Street number 11, Jagjeet Nagar, North East Delhi, New
                  Delhi, 110053 India
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </q-footer>
</template>

<script>
import { defineComponent, ref } from "vue";
import footer1 from "../assets/images/footerImages/footer1.svg";
import footer2 from "../assets/images/footerImages/footer2.svg";
import footer3 from "../assets/images/footerImages/footer3.svg";
import footer4 from "../assets/images/footerImages/footer4.svg";
import arrowRight from "../assets/images/footerImages/footer-arrow-right.svg";
export default defineComponent({
  name: "AppFooter",
  setup() {
    const footerDetails = ref([
      {
        src: footer1,
        name: "해외 개발자 원격 채용",
      },
      {
        src: footer2,
        name: "외국인 원격 채용 (비개발)",
      },
      {
        src: footer3,
        name: "한국어 가능 외국인 채용",
      },
      {
        src: footer4,
        name: "해외 개발자 활용 서비스",
      },
    ]);
    return {
      footerDetails,
      arrowRight,
    };
  },
});
</script>

<style lang="scss" scoped>
.footer {
  background-color: #fbfbfb;
  color: #343741;
  position: static !important; /* Override fixed positioning */
  @media (max-width: 600px) {
    padding: 20px;
    padding-top: 40px;
    height: 900px;
  }
  @media (min-width: 601px) {
    padding-top: 60px;
    height: 400px;
  }
}
.remove-fixed-bottom {
  max-width: 1200px;
  margin: 0px auto; /* Center align content */
}
.detail-text {
  margin-bottom: 4px;
}
.detail-text-for {
  margin-bottom: 4px;
  margin-left: 15px;
}
.my-card {
  margin-bottom: 7px;
  @media (max-width: 600px) {
    width: 160px;
    height: 163px;
  }
  @media (min-width: 601px) {
    width: 187px;
    height: 142px;
  }
}
.cards-row {
  margin-bottom: 4px;
}
.click-div {
  color: #5e626f;

  @media (max-width: 600px) {
    margin-top: 25px;
  }
  @media (min-width: 601px) {
    margin-top: 15px;
  }
}
</style>
