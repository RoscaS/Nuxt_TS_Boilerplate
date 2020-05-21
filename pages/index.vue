<template>
  <v-content>
    <v-container class="fill-height" fluid>
      <h1>{{ title }}</h1>
      <v-row class="mt5" align="center">
        <v-btn class="text-capitalize" color="info" @click="buttonTest" text>
          Axios
        </v-btn>
      </v-row>
      <v-row class="mb5" align="center">
        <Logo />
      </v-row>
      <v-row class="mb5" align="center">
        <a href="#">Link test</a>
      </v-row>
    </v-container>
  </v-content>
</template>

<script lang="ts">
import { Vue, Component, Prop, Watch } from 'nuxt-property-decorator';

import Logo from '~/components/Logo.vue';

@Component({ components: { Logo } })
export default class Index extends Vue {
  title = 'Nuxt class API, Typescript, Vuetify';

  buttonTest() {
    this.$axios.$get('users').then(res => console.log(res));
  }
}
</script>
