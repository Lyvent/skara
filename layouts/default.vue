<template>
  <v-app>
    <Navbar />

    <v-main>
      <nuxt />
    </v-main>
  </v-app>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api';

// Components
import Navbar from '@/components/Navbar.vue';

export default defineComponent({
  name: 'default',
  components: {
    Navbar
  }
});
</script>