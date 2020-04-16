<template>
  <v-card class="ma-10" max-width="500px">
    <v-img class="white--text align-end" height="200px" :src="news.imageLink"></v-img>

    <v-card-title>{{ news.title }}</v-card-title>
    <v-card-subtitle>{{ news.date }}</v-card-subtitle>
    <v-card-text class="black--text">{{ news.shortText }}</v-card-text>

    <v-card-actions>
      <v-tooltip right>
        <template v-slot:activator="{ on }">
          <v-btn icon color="green" @click="liked=!liked" v-on="on">
            <v-icon>{{ liked==true? 'favorite' : 'favorite_border' }}</v-icon>
          </v-btn>
        </template>
        <span class="content">Like</span>
      </v-tooltip>

      <v-tooltip right>
        <template v-slot:activator="{ on }">
          <v-btn icon color="green" @click="saved=!saved" v-on="on">
            <v-icon>{{ saved==true? 'star' : 'star_border' }}</v-icon>
          </v-btn>
        </template>
        <span class="content">save</span>
      </v-tooltip>

      <v-tooltip right>
        <template v-slot:activator="{ on }">
          <v-btn icon color="green" v-on="on">
            <v-icon>share</v-icon>
          </v-btn>
        </template>
        <span class="content">share</span>
      </v-tooltip>
    </v-card-actions>
  </v-card>
</template>

<script lang="ts">
import Vue from "vue";
export default Vue.extend({
  name: "news-post",

  props: ["news"],

  data() {
    return {
      saved: false,
      liked: false
    };
  }
});
</script>