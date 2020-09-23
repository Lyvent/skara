<template>
  <v-container
    id="landing"
    class="text-center content"
  >
    <h1 class="text-h1 mb-2 font-weight-bold"
    >Lyvent.</h1>

    <p class="text-h6">
      Join a growing community of people
      <br />
      living and sharing the moment. 🌈🌿
    </p>

    <v-text-field
      rounded
      outlined
      class="search"
      append-icon="mdi-magnify"
      placeholder="Search stories"
      hint="Still figuring what to write here..."
    ></v-text-field>

    <v-row align="center" justify="center">
      <v-col
        md="3"
        cols="12"
        v-for="option in options"
        :key="option.title"
      >

        <v-card
          @click="viewPage()"
          class="rounded-lg text-left option"
          elevation="5"
        >
          <img :src="getSVG(option.svgName)" class="option-img"/>
          <v-divider />

          <v-card-title>
            {{ option.title }}
            <v-spacer />
            <v-icon v-text="option.icon" />
          </v-card-title>

          <v-card-text>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolor, nisi.
          </v-card-text>
        </v-card>

      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import { defineComponent } from '@vue/composition-api';

// Interfaces
interface Option {
  title: string;
  svgName: string;
  icon: string;
  description: string;
}

// Functions
const getSVG = (svgName: string) => {
  return require(`~/assets/Index/${ svgName }`);
};

const viewPage = () => {
  console.log('Implement');
};

export default defineComponent({
  name: 'index',
  layout: 'empty',

  setup() {
    const options: Array<Option> = [
      {
        title: 'Join',
        svgName: 'Join.svg',
        icon: 'mdi-account-multiple-plus',
        description: 'Lorem 10'
      },
      {
        title: 'Explore',
        svgName: 'Explore.svg',
        icon: 'mdi-compass',
        description: 'Lorem 10'
      },
      {
        title: 'About',
        svgName: 'About.svg',
        icon: 'mdi-account',
        description: 'Lorem 10'
      }
    ];

    return {
      options,

      // Functions
      getSVG,
      viewPage,
    }
  },

  head() {
    return {
      title: 'Welcome to Lyvent ✨'
    }
  }
});
</script>

<style lang="scss" scoped>
#landing {
  height: 80vh;
  margin-top: 2em;

  .search {
    max-width: 23em;
    margin: 0 auto;
  }

  .option {
    &-img {
      width: 100%;
      padding: 2em;
      height: 13em;
    }
  }
}
</style>