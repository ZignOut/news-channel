<template>
  <v-container>
    <h2 class="title font-weight-light">What's Latest Today</h2>

    <v-row class="py-5">
      <div class="#draftContents"></div>
    </v-row>

    <v-row>
      <v-text-field
        v-show="show.title"
        v-model="input"
        label="title"
        outlined
        @keypress.enter.exact.prevent
        @keypress.enter.exact="AddItem('title');"
      ></v-text-field>

      <v-text-field
        v-show="show.paragraph"
        v-model="input"
        label="paragraph"
        outlined
        @keypress.enter.exact.prevent
        @keypress.enter.exact="AddItem('paragraph');"
      ></v-text-field>
    </v-row>

    <!-- Dynamic Input Buttons -->
    <v-row>
      <v-btn-toggle>
        <v-tooltip bottom>
          <template v-slot:activator="{ on }">
            <v-btn v-on="on" color="green" @click="PrepareItem('title')">
              <v-icon>maximize</v-icon>
            </v-btn>
          </template>
          <span>Title</span>
        </v-tooltip>

        <v-tooltip bottom>
          <template v-slot:activator="{ on }">
            <v-btn v-on="on" color="green" @click="PrepareItem('paragraph')">
              <v-icon>mdi-pencil</v-icon>
            </v-btn>
          </template>
          <span>Paragraph</span>
        </v-tooltip>

        <v-tooltip bottom>
          <template v-slot:activator="{ on }">
            <v-btn v-on="on" color="green">
              <v-icon>add_photo_alternate</v-icon>
            </v-btn>
          </template>
          <span>Image</span>
        </v-tooltip>
      </v-btn-toggle>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "WritePost",

  data() {
    return {
      contents: "",
      input: "",
      inputArea: "",
      show: {
        title: false,
        subtitle: false,
        paragraph: false,
        image: false
      }
    };
  },

  methods: {
    PrepareItem: function(itemName) {
      switch (itemName) {
        case "title":
          this.show.title = true;
          break;

        case "paragraph":
          this.show.paragraph = true;
          break;

        default:
          break;
      }
    },

    AddItem: function(itemName) {
      switch (itemName) {
        case "title":
          this.contents += `<h1 class="">${this.input}</h1><br>`;
          this.show.title = false;
          break;

        case "paragraph":
          this.contents += `<p class="">${this.input}</p>`;
          this.show.title = false;
          break;

        default:
          break;
      }
    }
  },
};
</script>