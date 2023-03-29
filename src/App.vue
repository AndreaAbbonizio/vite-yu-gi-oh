<script>
import { store } from "./store.js";
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppLoader from './components/AppLoader.vue';
export default {
  data() {
    return {
      store,
    }
  },
  components: {
    AppHeader,
    AppMain,
    AppLoader,
  }
}
</script>

<template>
  <div>
    <AppLoader v-if="!store.cards.length > 0"></AppLoader>
    <AppHeader></AppHeader>
    <AppMain></AppMain>
  </div>
</template>

<style scoped></style>
