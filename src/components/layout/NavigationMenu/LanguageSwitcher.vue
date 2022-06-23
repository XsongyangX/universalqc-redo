<template>
  <section>
    <button><img :src="require('@/assets/images/layout/language icon.svg')" alt="Language selection" />en</button>
    <ul>
      <li>en</li>
      <li>fr</li>
    </ul>
  </section>
</template>

<style lang="scss" scoped>
section {
  position: relative;
  display: inline-block;
}

ul {
  display: none;
  position: absolute;
  background-color: #f1f1f1;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  z-index: 1;

  // no bullet
  list-style-type: none;
  padding: 0;
}

/* Show the dropdown menu on hover */
section:hover ul {
  display: block;
}

button {
  font-family: 'Open Sans';
  font-style: normal;
  font-weight: 700;
  font-size: 24px;
  line-height: 49px;
  display: flex;
  align-items: center;
  text-align: center;

  color: #000000;

  background-color: white;
  border: none;
}

li {
  padding-left: 10px;
  padding-right: 10px;

  font-family: 'Open Sans';
  font-style: normal;
  font-weight: 700;
  font-size: 24px;
  line-height: 49px;
  display: flex;
  align-items: center;
  text-align: center;

  color: #000000;
}

/* Change color of dropdown links on hover */
li:hover {
  background-color: #ddd;
  cursor: pointer;
}
</style>

<script lang="ts">
import { Options, Vue } from 'vue-class-component';

@Options({
  components: {
  },
})
export default class LanguageSwitcher extends Vue { }
</script>