<template>
  <div id="app">
    <header>
      <h1>Vue Wild Swipe</h1>
      <select v-model="imageSet">
        <option value="nature">Nature</option>
        <option value="urban">Urban</option>
        <option value="technology">Technology</option>
      </select>
      <nav>
        <a target="_blank" rel="noopener noreferrer" href="https://github.com/bhubr/vue-wild-swipe-example">GitHub (example)</a>
        <a target="_blank" rel="noopener noreferrer" href="https://github.com/bhubr/vue-wild-swipe">GitHub (lib)</a>
      </nav>
    </header>
    <div class="swipe-wrapper">
      <vue-wild-swipe :images="images"></vue-wild-swipe>
    </div>
  </div>
</template>

<script>
import VueWildSwipe from 'vue-wild-swipe'
import imageSets from './data/image-sets.json'

export default {
  name: 'App',
  components: {
    VueWildSwipe
  },
  data() {
    return {
      imageSet: 'nature'
    }
  },
  computed: {
    images() {
      return imageSets[this.imageSet]
    }
  }
}
</script>

<style>
@import './styles/icons.css';

body {
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#app > header {
  display: flex;
  width: 100%;
  justify-content: space-between;
  padding: 0.25em 0.5em;
  box-sizing: border-box;
}
#app > header > h1 {
  font-size: 14px;
}
#app > header > nav {
  display: flex;
  align-items: center;
}
#app > header > nav > a {
  margin: 0 0.25em;
}
.swipe-wrapper {
  height: calc(100vh - 60px);
}
.swipe-wrapper .vue-wild-swipe .container {
  /* Compensate the bullets, added afterwards */
  height: calc(100% - 18px);
}
</style>
