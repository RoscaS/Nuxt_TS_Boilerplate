<template lang="pug">
  
  v-content
    v-container.fill-height(fluid)
      h1 {{ title }}
      v-row.mt5(align="center")
        v-btn.text-capitalize(
          color="info",
          @click="buttonTest",
          text
        )
          | lorem
      v-row.mb5(align="center")
        Logo
      v-row.mb5(align="center")
        a(href="#") Link test
    
  
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

<style lang="scss" scoped></style>
