<template>
  <v-app>
    <v-app-bar app class="bg-background-dark text-light"  color="#37474F" dark>
      <v-app-bar-nav-icon @click="toggleDrawer"></v-app-bar-nav-icon>
      <v-toolbar-title>Animated Navbar</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-col >
    
        <v-btn class="icon-button md:flex hidden" icon>
          <v-icon fill="dark">mdi-account</v-icon>
        </v-btn>
        <v-btn icon class="icon-button md:flex hidden custom-btn">
          <v-icon>mdi-cart-outline</v-icon>
        </v-btn>
      </v-col>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" app>
      <v-list>
        <v-list-item v-for="(item, index) in items" :key="index" link>
          <v-list-item-icon>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title>{{ item.text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </v-app>
</template>

<script lang="ts">
export default {
  data() {
    return {
      drawer: false,
      items: [
        { text: "Home", icon: "mdi-home" },
        { text: "About", icon: "mdi-information" },
        { text: "Services", icon: "mdi-cogs" },
        { text: "Contact", icon: "mdi-email" },
      ],
    };
  },
  methods: {
    toggleDrawer() {
      this.drawer = !this.drawer;
    },
  },
};
</script>

<style scoped>
.custom-btn:hover {
  background-color: #FFC107; 
  color: #000000; 
}
</style>
