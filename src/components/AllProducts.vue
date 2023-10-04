<template>
  <v-container>
    <v-row>
      <v-col cols="3"></v-col>
      <v-col cols="3">
        <v-text-field
          variant="outlined"
          placeholder="Search product(s)...."
          prepend-inner-icon="mdi-magnify"
        />
      </v-col>
      <v-col cols="3">
        <v-select variant="outlined" placeholder="--Trier par--"></v-select>
      </v-col>
      <v-col cols="3"></v-col>
    </v-row>

    <v-row>
      <v-col v-for="(variant, i) in variants" :key="i">
        <v-card class="mx-auto" max-width="344" :variant="variant">
          <v-card-item>
            <div>
              <div class="text-overline mb-1">
                {{ variant }}
              </div>
              <div class="text-h6 mb-1">Headline</div>
              <div class="text-caption">
                Greyhound divisely hello coldly fonwderfully
              </div>
            </div>
          </v-card-item>

          <v-card-actions>
            <v-btn> Button </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
export default {
  data() {
    return {
      searchProduct: "",
      variants: ["elevated", "flat", "tonal", "outlined"],
    };
  },
  components: {},
  methods: {},
};
</script>

<style lang="scss" scoped></style>
