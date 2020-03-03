<template>
  <div id="app">
    <intro />
  </div>
</template>

<script>
import intro from "./components/intro.vue";

export default {
  name: "App",
  components: {
    intro
  }
};
</script>

<style lang="sass">

@import "./assets/fonts/stylesheet.css"
@import "./assets/sass/variables"

*
  margin: 0
  padding: 0
  box-sizing: border-box

a
  text-decoration: none
  color: $font

.btn
  width: 180px
  padding: 12.5px
  border-radius: 3px
  background-color: $yellow
  display: flex
  align-items: center
  justify-content: center
  font: 500 18px $montserrat
  box-shadow: -2px 3px 4px 1px $shadow
#app
  font-family: $bebas
  text-align: center
  color: $font
</style>
