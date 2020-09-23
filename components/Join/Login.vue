<template>
  <v-row
    id="login"
    align="stretch"
  >
    <v-col
      sm="12"
      md="5"
    ><v-container class="left">
      <div class="text-h3 font-weight-bold mb-2">
        Login
      </div>
      <p>Welcome back, we're glad to see you again!</p>

      <v-text-field
        outlined
        label="Email"
        v-model="loginData.email"
      ></v-text-field>

      <v-text-field
        outlined
        label="Password"
        :type="showPassword ? 'text' : 'password'"
        :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
        @click:append="showPassword = !showPassword"
        v-model="loginData.password"
      ></v-text-field>

      <v-btn
        block
        x-large
        dark
        color="deep-purple"
        elevation="10"
      >Login</v-btn>

      <p class="register">
        Dont have an account?
        <NuxtLink to="">Register</NuxtLink>
      </p>
    </v-container>
    </v-col>

    <v-col
      md="7"
      cols="12"
      class="right hidden-sm-and-down"
    ></v-col>
  </v-row>
</template>

<script lang="ts">
import { defineComponent, ref, reactive } from '@vue/composition-api';

export default defineComponent({
  name: 'join',
  layout: 'empty',

  setup() {
    const showPassword = ref(false);
    const loginData = reactive({
      email: '',
      password: '',
    })

    return { loginData, showPassword };
  },

  head() {
    return {
      title: 'Join Lyvent 🚀'
    }
  }
});
</script>

<style lang="scss" scoped>
#login {
  height: 100vh;

  .left {
    padding-top: 4em;
    padding: 8em 3.5em;
  }

  .register {
    margin-top: 1em;

    a {
      color: purple;
      text-decoration: none;
    }
  }
}
</style>