<template>
  <NavigationMenu></NavigationMenu>
  <router-view />
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import NavigationMenu from './components/layout/NavigationMenu/NavigationMenu.vue';

@Options({
  components: {
    NavigationMenu
  },
})
export default class HomeView extends Vue { }
</script>