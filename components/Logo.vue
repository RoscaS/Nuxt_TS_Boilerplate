<template>
  <v-btn text color="info" @click="axiosTest">Axios component</v-btn>
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
  async axiosTest() {
    let x = await this.$axios.$get('users');
    console.log(x);
  }
}
</script>

<style lang="scss">

</style>
