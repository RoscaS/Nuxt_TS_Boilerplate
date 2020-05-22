<template lang="pug">

  v-app
    v-app-bar(:clipped-left='clipped', fixed='', app='')
      v-btn(icon='', @click.stop='miniVariant = !miniVariant')
        v-icon mdi-{{ `chevron-${miniVariant ? 'right' : 'left'}` }}
      v-btn(icon='', @click.stop='clipped = !clipped')
        v-icon mdi-application
      v-btn(icon='', @click.stop='fixed = !fixed')
        v-icon mdi-minus
      v-toolbar-title(:v-text='title')
        v-spacer
          v-btn(icon='', @click.stop='rightDrawer = !rightDrawer')
            v-icon mdi-menu
    v-content
      v-container
        nuxt
    v-navigation-drawer(v-model='rightDrawer', :right='right', temporary='', fixed='')
      v-list
        v-list-item(@click.native='right = !right')
          v-list-item-action
            v-icon(light='')
              | mdi-repeat
          v-list-item-title Switch drawer (click me)
    v-footer(:fixed='fixed', app='')
      span © {{ new Date().getFullYear() }}
    

</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator';

@Component
export default class Default extends Vue {
  title: string = 'Vuetify';
  clipped: boolean = false;
  drawer: boolean = false;
  fixed: boolean = false;
  miniVariant: boolean = false;
  right: boolean = true;
  rightDrawer: boolean = false;
  items: object[] = [
    {
      icon: 'mdi-apps',
      title: 'Welcome',
      to: '/'
    },
    {
      icon: 'mdi-chart-bubble',
      title: 'Inspire',
      to: '/inspire'
    }
  ];
}
</script>

<style lang="scss" scoped></style>
