<template>
  <div class="layout">
    <div class="layout-body">
      <RouterView :key="$route.path" />
    </div>
    <div class="layout-footer">
     <navigation/>
    </div>
  </div>
</template>

<script lang="ts">
import Navigation from './components/Navigation.vue';
  export default {
components: {
  Navigation
}
  }
</script>
<style scoped>
.layout {
  display: flex;
  justify-content: center;
  flex-direction: column;
  &-body {
    padding: 0.5rem;
    margin: 3rem auto 0;
  }
}
</style>
