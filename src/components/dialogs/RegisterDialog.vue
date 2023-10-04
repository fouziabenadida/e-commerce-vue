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
            Register
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
          label="E-mail"
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
      <v-col>
        <v-text-field
          variant="outlined"
          label="Password"
          color="Repeat password"
        ></v-text-field>
      </v-col>
      <v-col>
        <v-checkbox
          class="mr-4"
          label="I agree to terms and conditions"
          color="primary"
          hide-details
        ></v-checkbox>
      </v-col>
      <v-col class="ma-0">
        <v-btn color="primary" width="100%" elevated>Register</v-btn>
      </v-col>
    </v-card>
  </v-dialog>
</template>

<script lang="ts">
export default {
  name: "RegisterDialog",
  data() {
    return {
      openDialog: false,
    };
  },
  methods: {
    closeDialog() {
      this.$emit("closeRegisterDialog", false);
    },
  },
};
</script>

<style scoped></style>
