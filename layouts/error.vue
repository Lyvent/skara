<template>
  <v-app>
    <h1 v-if="errorMessage">
      {{ errorMessage }}
    </h1>

    <NuxtLink to="/">
      Index Page
    </NuxtLink>
  </v-app>
</template>

<script lang="ts">
import { computed, defineComponent } from '@vue/composition-api';

export default defineComponent({
  layout: 'empty',

  props: {
    error: {
      type: Object,
      default: null
    }
  },

  setup({ error }) {
    const errorMessage = computed(() => {
      return error.statusCode === 404 ? '404 Not found' : 'An error occurred';
    });

    return { errorMessage }
  },
});
</script>

<style scoped>
h1 {
  font-size: 20px;
}
</style>
