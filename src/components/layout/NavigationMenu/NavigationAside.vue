<template>
  <header>
    <nav>
      <ul>
        <li style="margin-left: 0" id="logo">
          <router-link to="/"><img :src="require('@/assets/images/layout/logo.png')" alt="Logo of the Universal Party">
          </router-link>
        </li>
        <li style="margin-right: 0" id="menu">
          <img @click="openNav()" :src="require('@/assets/images/layout/menu icon.svg')" alt="Menu button">
        </li>
      </ul>
    </nav>
  </header>
  <main>
    <aside ref="sidenav">
      <header>
        <!-- LOGO -->
        <router-link to="/" @click="closeNav()">
          <img :src="require('@/assets/images/layout/logo.png')" alt="Logo of the Universal Party">
        </router-link>
        <!-- Party name -->
        <h1>
          <p>UNIVERSAL PARTY</p>
        </h1>
        <!-- Close button -->
        <img style="background: rgba(37, 37, 37, 0.96);" @click="closeNav()"
          :src="require('@/assets/images/layout/close_button.svg')" alt="Close aside menu">
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
  </main>
</template>

<style lang="scss" scoped>
.no-underscore {
  text-decoration: none;
}

header {

  nav {

    // display only when on mobile
    @media only screen and (min-width: 795px) {
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

  li:hover:not(#logo):not(#menu) {
    background-color: #7733DE;

    h1 {
      color: white;
    }
  }
}

main {
  aside {

    // display only when called
    // Modified through script
    width: 0;

    // follows the scroll
    position: fixed;
    right: 0;
    top: 0;

    // opacity mask
    background: rgba(37, 37, 37, 0.86);

    overflow-x: hidden;
    /* Disable horizontal scroll */
    transition: 0.5s;
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
export default class NavigationAside extends Vue {
  openNav(): void {
    (this.$refs.sidenav as HTMLElement).style.width = "100%";
    // (this.$refs.sidenav as HTMLElement).style.display = "block";
  }

  closeNav(): void {
    (this.$refs.sidenav as HTMLElement).style.width = "0";
    // (this.$refs.sidenav as HTMLElement).style.display = "none";
  }
}
</script>