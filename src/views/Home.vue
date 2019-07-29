<template>
  <div class="home">
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
  name: 'home',
  components: {
    Slider,
    BtnInvertColors,
    BtnInfo
  }
}
</script>

<style lang="scss" scoped>
.home {
  display: grid;
  grid-template-rows: 90vh 1fr;
  align-items: center;
  width: 100%;
  height: 100vh;
  min-height: 30rem;
  padding: 1rem;
}
</style>
