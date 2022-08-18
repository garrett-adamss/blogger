<template>
  <main>
    <router-view />
  </main>
</template>

<script>
import { computed } from 'vue';
import { AppState } from './AppState';
import ProfilePage from './pages/ProfilePage.vue';

export default {
  name: "App",
  setup() {
    return {
      appState: computed(() => AppState)
    };
  },
  components: { ProfilePage }
}
</script>
<style lang="scss">
@import "./assets/scss/main.scss";
</style>
