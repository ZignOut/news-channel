<template>
  <v-app>
    <!-- Navigation Drawer -->
    <v-navigation-drawer expand-on-hover color="green" :clipped="$vuetify.breakpoint.lgAndUp" app>
      <v-list v-for="navItem in navItems" :key="navItem" dense nav class="py-0">
        <v-list-item>
          <v-btn
            :ripple="false"
            block
            depressed
            color="green white--text"
            class="pl-0"
            :href="navItem.destination"
          >
            <v-list-item-icon>
              <v-icon>{{ navItem.icon }}</v-icon>
            </v-list-item-icon>

            <v-list-item-content class="caption">{{ navItem.title }}</v-list-item-content>
          </v-btn>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>

    <!-- ToolBar -->
    <v-app-bar color="white" elevation="0" dense app :clipped-left="$vuetify.breakpoint.lgAndUp">
      <v-toolbar-title>
        <v-btn :ripple="false" depressed href="/">
          <span class="title green--text text-uppercase">News</span>
          <span>Channel</span>
        </v-btn>
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-menu left bottom offset-y>
        <template v-slot:activator="{ on }">
          <v-btn icon v-on="on">
            <v-icon>mdi-dots-vertical</v-icon>
          </v-btn>
        </template>

        <v-list>
          <v-list-item v-for="menu in menus" :key="menu">
            <v-list-item-icon>
              <v-icon>{{ menu.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-title>{{ menu.title }}</v-list-item-title>
          </v-list-item>
        </v-list>
      </v-menu>
    </v-app-bar>

    <v-content>
      <router-view></router-view>
    </v-content>
  </v-app>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "App",

  data: () => ({
    navItems: [
      { title: "Home", icon: "home", destination: "/" },
      { title: "about", icon: "info", destination: "/about" },
      { title: "Newsfeed", icon: "mdi-newspaper", destination: "/newsfeed" },
      { title: "Channels", icon: "mdi-globe-model", destination: "channels" }
    ],

    menus: [
      { title: "manage account", icon: "person" },
      { title: "Setting", icon: "settings" },
      { title: "Log Out", icon: "mdi-export" }
    ]
  })
});
</script>
