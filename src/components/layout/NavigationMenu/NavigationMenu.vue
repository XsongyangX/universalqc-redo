<template>
  <NavigationBar></NavigationBar>
</template>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import NavigationBar from '@/components/layout/NavigationMenu/NavigationBar.vue'

@Options({
  components: {
    NavigationBar
  },
})
export default class NavigationMenu extends Vue { }
</script>