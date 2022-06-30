<template>
  <!-- Large nav for desktop -->
  <nav>
    <ul>
      <li style="margin-left: 0" id="logo">
        <img :src="require('@/assets/images/layout/logo.png')" alt="Logo of the Universal Party">
      </li>
      <li>
        <router-link to="/platform" class="no-underscore">
          <h1>Platform</h1>
        </router-link>
      </li>
      <li>
        <router-link to="/people" class="no-underscore">
          <h1>Candidates 2022</h1>
        </router-link>
      </li>
      <li>
        <router-link to="/donate-volunteer" class="no-underscore">
          <h1>Donate</h1>
        </router-link>
      </li>
      <li>
        <router-link to="/contact" class="no-underscore">
          <h1>Contact</h1>
        </router-link>
      </li>
      <li>
        <router-link to="/about" class="no-underscore">
          <h1>About</h1>
        </router-link>
      </li>
      <li id="language-droplist">
        <LanguageSwitcher></LanguageSwitcher>
      </li>
    </ul>
  </nav>
</template>

<style scoped lang="scss">
.no-underscore {
  text-decoration: none;
}

nav {

  // display only when on desktop
  @media only screen and (max-width: 796px) {
    display: none;
  }

  // rectangular background
  position: fixed;
  width: 100%;
  height: 60px;
  // overflow: hidden;
  margin: 0;
  left: 0;
  top: 0;

  background: #FFFFFF;
  box-shadow: 0px 4px 4px rgba(0, 0, 0, 0.25);
}

ul {
  padding: 0;
  margin: 0;
  // no bullet
  list-style-type: none;

  // center the list elements
  display: flex;
}

li {
  // horizontal
  float: left;

  // center the list elements
  margin: auto;

  // animation
  transition: 0.3s;
}

// font for the links
h1 {
  font-family: 'Open Sans';
  font-style: normal;
  font-weight: 700;
  font-size: 24px;
  line-height: 49px;
  display: flex;
  align-items: center;
  text-align: center;

  color: #000000;

  // center the text
  margin: auto;
  margin-left: 10px;
  margin-right: 10px;

  // animation
  transition: 0.3s;
}

li:hover:not(#language-droplist):not(#logo) {
  background-color: #7733DE;

  h1 {
    color: white;
  }
}
</style>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';
import LanguageSwitcher from './LanguageSwitcher.vue';

@Options({
  components: {
    LanguageSwitcher
  },
})
export default class NavigationBar extends Vue { }
</script>