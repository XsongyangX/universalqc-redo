<template>
  <aside>
    <header>
      <!-- LOGO -->
      <router-link to="/">
        <img :src="require('@/assets/images/layout/logo.png')" alt="Logo of the Universal Party">
      </router-link>
      <!-- Party name -->
      <h1>
        <p>UNIVERSAL PARTY</p>
      </h1>
      <!-- Close button -->
      <img :src="require('@/assets/images/layout/close_button.svg')" alt="Close aside menu">
    </header>
    <nav>
      <!-- LINKS -->
      <router-link to="/platform" class="no-underscore">
        <h2>
          <p>PLATFORM</p>
        </h2>
      </router-link>
      <router-link to="/people" class="no-underscore">
        <h2>
          <p>CANDIDATES 2022</p>
        </h2>
      </router-link>
      <router-link to="/donate-volunteer" class="no-underscore">
        <h2>
          <p>DONATE & VOLUNTEER</p>
        </h2>
      </router-link>
      <router-link to="/about" class="no-underscore">
        <h2>
          <p>ABOUT</p>
        </h2>
      </router-link>
      <router-link to="/contact" class="no-underscore">
        <h2>
          <p>CONTACT US</p>
        </h2>
      </router-link>
      <h2>
        <LanguageSwitcher style="margin: auto;"></LanguageSwitcher>
      </h2>
    </nav>
    <!-- language switcher -->
  </aside>
</template>

<style lang="scss" scoped>
.no-underscore {
  text-decoration: none;
}

aside {

  // display only when on mobile
  @media only screen and (min-width: 797px) {
    display: none;
  }

  width: 100%;

  // follows the scroll
  position: fixed;
  left: 0;
  top: 0;

  // opacity mask
  background: rgba(37, 37, 37, 0.86);
}

header {
  display: flex;
  flex-direction: row;

  height: 61px;

  justify-content: space-between;
}

h1 {
  background-color: #7234CE;

  display: flex;

  width: 100%;
  margin: 0;
}

p {
  font-family: 'Open Sans';
  font-style: normal;
  font-weight: 700;
  font-size: 24px;
  line-height: 33px;
  display: flex;
  align-items: center;
  text-align: center;

  color: #FFFFFF;

  margin: auto;
}


nav {
  display: flex;
  flex-direction: column;
}

h2 {
  margin: 0;
  height: 69px;

  display: flex;
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
export default class NavigationAside extends Vue { }
</script>