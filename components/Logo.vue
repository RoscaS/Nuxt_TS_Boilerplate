<template>
  <h1><a @click="buttonTest">{{ title }}</a></h1>
</template>

<script lang="ts">
import { Vue, Component, Prop, Watch } from 'nuxt-property-decorator'

@Component
export default class Logo extends Vue {
  login: string = ''
  password: string = ''
  title: string = 'Logo component'

  /*------------------------------------------------------------------*\
  |*							    Hooks
  \*------------------------------------------------------------------*/

  asyncData(): void {}

  beforeUpdate(): void {}

  mounted(): void {}

  /*------------------------------------------------------------------*\
  |*							    Methodes
  \*------------------------------------------------------------------*/
  async buttonTest() {
    let x = await this.$axios.$get('users');
    console.log(x);
  }
}
</script>

<style>
.NuxtLogo {
  animation: 1s appear;
  margin: auto;
}

@keyframes appear {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
</style>
