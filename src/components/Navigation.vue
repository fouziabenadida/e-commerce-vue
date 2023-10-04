<template>
  <v-app>
    <v-app-bar app class="bg-background-dark text-light" color="#37474F" dark>
      <v-app-bar-nav-icon @click="toggleDrawer"></v-app-bar-nav-icon>
      <v-toolbar-title
        style="
          font-size: large;
          font-family: Georgia, 'Times New Roman', Times, serif;
        "
        >Trabajando</v-toolbar-title
      >
      <v-spacer></v-spacer>
      <v-col>
        <v-menu>
          <template v-slot:activator="{ props }">
            <v-btn
              v-bind="props"
              class="icon-button md:flex hidden"
              icon="mdi-account"
              style="background-color: #37474f"
            >
            </v-btn>
          </template>
          <v-card
            class="overflow-hidden"
            width="250px"
            height="20vh"
            style="background-color: #37474f; padding: 0"
            :border="false"
          >
            <v-card-title class="text-center">
              <v-btn
              @click="loginDialog = true"
                width="100%"
                max-height="100px"
                color="#F5AB3D"
                class="pa-2 mt-2 custom-btn"
                >Log in</v-btn
              >
            </v-card-title>
            <p
              class="ma-1 text-center"
              style="font-size: 16px; font-family: sans-serif; color: #cccccc"
            >
              Dont' have an account yet?
            </p>
            <v-card-title class="text-center">
              <v-btn
              @click="registerDialog = true"
                width="100%"
                style="color: #f5ab3d; border: #f5ab3d"
                class="pa-2 mt-2 register-btn"
                >Register</v-btn
              >
            </v-card-title>
          </v-card>
        </v-menu>

        <v-btn icon class="icon-button md:flex hidden custom-btn">
          <v-icon class="md:flex hidden">mdi-cart-outline</v-icon>
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
<login-dialog v-model="loginDialog"  @closeDialog="($event: any) => (loginDialog = $event)"/>
<register-dialog v-model="registerDialog" @closeRegisterDialog="($event: any) => (registerDialog = $event)"/>
  </v-app>
</template>

<script lang="ts">
import LoginDialog from './dialogs/LoginDialog.vue';
import RegisterDialog from './dialogs/RegisterDialog.vue'
export default {
  name: "Navigation",
  components: {
    LoginDialog,
    RegisterDialog
  },
  data() {
    return {
      drawer: false,
      menu: false,
      loginDialog: false,
      registerDialog: false,
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
  closeDialog() {
    this.loginDialog = false;
  }
  },
};
</script>

<style scoped>
.custom-btn {
  background-color: #ffc107;
  color: #000000;
}
.register-btn:hover {
  background-color: #ffc107;
  color: #000000 !important;
  border-radius: 1px;
}
</style>
