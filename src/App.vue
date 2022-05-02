<template>
  <v-app>
    <MainPage />
  </v-app>
</template>

<script>
import Vue from "vue";
import MainPage from "./components/MainPage.vue";

export default Vue.extend({
  name: "App",

  components: {
    MainPage,
  },

  data: () => ({
    //
  }),
});
</script>
