<template>
    <main>
      <Slider></Slider>
    </main>
    <footer>
      <BtnInvertColors></BtnInvertColors>
      <BtnInfo></BtnInfo>
    </footer>
  </div>
</template>

<script>
import Slider from "@/components/Slider";
import BtnInvertColors from "@/components/BtnInvertColors";
import BtnInfo from "@/components/BtnInfo";

export default {
  name: 'app',
  components: {
    Slider,
    BtnInvertColors,
    BtnInfo
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
