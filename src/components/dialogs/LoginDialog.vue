<template>
  <v-dialog width="30%" class="pa-0">
    <v-card height="30%" class="overflow-hidden">
      <v-row align="center">
        <v-col>
          <v-card-title
            style="
              font-family: Cambria, Cochin, Georgia, Times, 'Times New Roman',
                serif;
              font-size: 36px;
              color: #333333;
            "
          >
            Login
          </v-card-title>
        </v-col>
        <v-col align="end" class="mr-4">
          <v-icon @click="closeDialog">mdi-close</v-icon>
        </v-col>
      </v-row>
      <v-col>
        <v-text-field
          variant="outlined"
          label="Username"
          color="primary"
        ></v-text-field>
      </v-col>
      <v-col>
        <v-text-field
          variant="outlined"
          label="Password"
          color="primary"
        ></v-text-field>
      </v-col>
      <v-col class="ma-0">
        <v-btn color="primary" width="100%" elevated>Log in</v-btn>
      </v-col>
    </v-card>
  </v-dialog>
</template>

<script lang="ts">
export default {
  name: "LoginDialog",
  data() {
    return {
      openDialog: false,
    };
  },
  methods: {
    closeDialog() {
      this.$emit("closeDialog", false);
    },
  },
};
</script>

<style scoped></style>
