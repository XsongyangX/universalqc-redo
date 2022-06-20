<template>
  <div class="home">
    Home!
  </div>
</template>

<style>
.home {
  color: black;
}
</style>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  components: {
  },
})
export default class HomeView extends Vue { }
</script>
