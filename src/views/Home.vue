<template>
  <div>
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