<template lang="pug">
v-container(class='cbx-container')
  v-row(no-gutters=true class="qwe")
    v-layout(row)
      v-col(
        cols="12"
        sm="6"
        md="4")
        v-combobox(class="rounded-lg ml-auto"
          v-model="searchWord"
          :items="getDisplayedDoctors"
          :label='placeholder'
          :placeholder="placeholder"
          item-text="title"
          rounded=false
          clearable
          outlined
          background-color="#f2f8ff")
          template(v-slot:prepend-item)
            v-list-item
              span(class="text--disabled") {{ profession }}
          template(v-slot:no-data)
            v-list-item
              span {{ noDataText }}
      v-col(
        cols="12"
        sm="6"
        md="4")
        v-btn(class="pr-6 pl-6 rounded-lg" 
          color="primary"  
          height="3.5rem") 
          span.btn-text {{ buttonText }}
</template>

<script lang="ts">
import { mapGetters } from "vuex";
import Vue from "vue";
import Options from "vue-class-component";
import {
  PROFESSION,
  NO_DATA_TEXT,
  BUTTON_TEXT,
  PLACEHOLDER,
} from "../store/constants/constants";

@Options({
  computed: {
    ...mapGetters("doctors", ["getDisplayedDoctors"]),
  },
})
export default class MainPage extends Vue {
  data(): Record<string, any> {
    return {
      searchWord: "",
      profession: PROFESSION,
      noDataText: NO_DATA_TEXT,
      buttonText: BUTTON_TEXT,
      placeholder: PLACEHOLDER,
    };
  }
}
</script>

<style lang="scss" scoped />
