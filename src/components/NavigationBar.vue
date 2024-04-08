<template>
  <q-header class="navigation">
    <q-toolbar class="flex justify-between">
      <img class="logo-image cursor-pointer" src="../assets/images/logoh.svg" />
      <div v-if="$q.screen.gt.sm" class="flex">
        <q-btn-dropdown
          color="primary"
          label="채용"
          class="text-white text-subtitle1 text-weight-bold"
          flat
          dropdown-icon="expand_more"
        >
          <q-list>
            <q-item clickable v-close-popup @click="onItemClick">
              <q-item-section>
                <q-item-label>해외 개발자 원격 채용</q-item-label>
              </q-item-section>
            </q-item>

            <q-item clickable v-close-popup @click="onItemClick">
              <q-item-section>
                <q-item-label>외국인 원격 채용 (비개발 직군)</q-item-label>
              </q-item-section>
            </q-item>

            <q-item clickable v-close-popup @click="onItemClick">
              <q-item-section>
                <q-item-label>한국어 가능 외국인 채용</q-item-label>
              </q-item-section>
            </q-item>
          </q-list>
        </q-btn-dropdown>
        <q-btn class="text-white text-subtitle1 text-weight-bold" flat
          >해외 개발자 활용 서비스
        </q-btn>
      </div>
      <q-btn
        v-if="$q.screen.gt.sm"
        unelevated
        border-radius="10px"
        rounded-borders
        class="text-info text-weight-bold bg-white rounded-borders"
        >문의하기</q-btn
      >
      <q-btn
        v-if="$q.screen.lt.md"
        flat
        rounded-borders
        dense
        icon="menu"
        class=""
      />
      <!-- Navigation Drawer -->
    </q-toolbar>
  </q-header>
</template>

<script>
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "NavigationBar",
  setup() {
    // State for controlling the drawer
    const drawerOpen = ref(false);

    // Method to open/close the drawer
    const openDrawer = () => {
      drawerOpen.value = !drawerOpen.value;
    };

    // Method to handle item click (if needed)
    const onItemClick = () => {
      // Implement item click logic here
    };

    return {
      drawerOpen,
      openDrawer,
      onItemClick,
    };
  },
});
</script>

<style lang="scss" scoped>
.navigation {
  background-color: transparent; /* Example background color for navigation */
  max-width: 1200px;
  margin: 0px auto; /* Center align content */
  color: white;
  @media (max-width: 600px) {
    padding: 20px;
  }
  @media (min-width: 601px) {
    padding: 15px;
  }
}
.q-list {
  border-radius: 8px;
}
.logo-image {
  width: 114px;
  height: 21px;
}
.q-btn.rounded-borders {
  border-radius: 8px;
}
</style>
