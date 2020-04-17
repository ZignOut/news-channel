<template>
  <div>
    <v-textarea
      autofocus
      type="text"
      rows="1"
      label="search"
      color="green"
      auto-grow
      clearable
      prepend-inner-icon="search"
      v-model="searchValue"
      @input="findKey"
      @keydown.enter.exact.prevent
      @keydown.enter.exact="$emit('search', searchValue); searchValue='';"
    ></v-textarea>

    <v-chip-group column active-class="green white--text">
      <v-chip v-for="(tag) in tags" :key="tag">{{ tag }}</v-chip>
    </v-chip-group>
  </div>
</template>

<script>
export default {
  name: "search-bar",

  props: ["searchKeys"],

  data() {
    return {
      searchValue: "",
      tags: []
    };
  },

  computed: {
    keys: function() {
      const categoriesKey = [];
      const postsKey = [];
      this.searchKeys.forEach(key => {
        categoriesKey.push(key.category);
        key.posts.forEach(post => {
          postsKey.push(post.title);
        });
      });
      const result = [...categoriesKey, ...postsKey];
      return result;
    }
  },

  methods: {
    findKey: function() {
      if (this.searchValue) {
        this.tags = this.keys.filter(sub =>
          sub.toLowerCase().includes(this.searchValue.toLowerCase())
        );
      } else {
        this.tags = [];
      }
    }
  }
};
</script>