<script setup>
import Nav_bar from './components/Nav_bar.vue'
import Main from './components/Main.vue'
</script>

<template>
  <div id="app">
    <Nav_bar/>
  <Main/>
  </div>
  
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}
#app {
    margin-top: 60px;
    width: 70%;
    margin: 0 auto;
  }

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
