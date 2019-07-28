<template>
      <Slider></Slider>
  </div>
</template>

<script>
import Slider from "@/components/Slider";

export default {
  name: 'app',
  components: {
    Slider,
  }
}
</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
