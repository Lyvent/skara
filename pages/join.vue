<template>
  <v-window id="join" v-model="window">
    <v-window-item>
      <Login />
    </v-window-item>
  </v-window>
</template>

<script lang="ts">
import { defineComponent, ref } from '@vue/composition-api';

// Import Login views
import Login from '@/components/Join/Login.vue';

export default defineComponent({
  name: 'join',
  layout: 'empty',
  components: {
    Login
  },

  setup() {
    const window = ref(0);

    return { window };
  }
});
</script>