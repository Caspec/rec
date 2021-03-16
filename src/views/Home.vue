<template>
  <div class="home">
   <Hero></Hero>
   <Info></Info>
   <Condo></Condo>
  </div>
</template>

<script>
// @ is an alias to /src
import Hero from "../components/Hero"
import Info from "../components/Info"
import Condo from "../components/Condo"
export default {
  name: "Home",
  components: {
    Hero,
    Info,
    Condo
  },
};
</script>

<style scoped>

</style>