<template>
  <!-- Large screens -->
  <NavigationBar></NavigationBar>

  <!-- Small screens -->
  <NavigationAside></NavigationAside>
</template>

<style lang="scss" scoped>
</style>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import NavigationBar from '@/components/layout/NavigationMenu/NavigationBar.vue'
import NavigationAside from '@/components/layout/NavigationMenu/NavigationAside.vue'

@Options({
  components: {
    NavigationBar,
    NavigationAside
  },
})
export default class NavigationMenu extends Vue { }
</script>