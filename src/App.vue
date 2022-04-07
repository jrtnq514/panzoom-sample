<template>
  <div id="app">
    <Panzoom>
      <!-- PUT THE IMAGE YOU WANT HERE -->
      <img alt="Vue logo" src="./assets/logo.png">
<!--   Uncomment to use SVG   -->
<!--      <svg viewBox="0 0 10 10" x="200" width="100">-->
<!--        <circle cx="5" cy="5" r="4" />-->
<!--      </svg>-->
    </Panzoom>
  </div>
</template>

<script>
import Panzoom from "@/components/Panzoom";

export default {
  name: 'App',
  components: {
    Panzoom,
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
