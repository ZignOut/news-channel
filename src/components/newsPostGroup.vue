<template>
  <v-container>
    <v-tabs v-model="tab" color="green">
      <v-tab v-for="news in newsGroup" :key="news.category" class="subtitle-2">{{ news.category }}</v-tab>
    </v-tabs>

    <v-tabs-items v-model="tab">
      <v-tab-item v-for="news in newsGroup" :key="news.posts">
        <news-post :news="newsPost" v-for="newsPost in news.posts" :key="newsPost" class="d-inline-block"></news-post>
      </v-tab-item>
    </v-tabs-items>
  </v-container>
</template>

<script lang="ts">
import Vue from "vue";
import newsPostVue from "./newsPost.vue";
export default Vue.extend({
  name: "news-post-group",

  props: ["allNews"],

  components: {
    "news-post": newsPostVue
  },

  data() {
    return {
      tab: null,
      newsGroup: this.allNews
    };
  }
});
</script>