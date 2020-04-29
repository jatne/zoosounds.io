<template>
  <swiper
    ref="animalSlider"
    v-swiper:animalSlider="swiperOptions"
    @ready="handleSlideChange"
    @slideChange="handleSlideChange"
  >
    <swiper-slide v-for="(animal, index) in this.animals" v-bind:key="index">
      <div v-on:click="playSound(index)">
        <img :src="require(`@/assets/zoo/images/${animal.image}`)" v-bind:alt="animal.name" />
        <audio
          v-bind:src="require(`@/assets/zoo/sounds/${animal.sound}`)"
          v-bind:data-animal="index"
        ></audio>
      </div>
    </swiper-slide>
  </swiper>
</template>
<script>
import { Swiper, SwiperSlide, directive } from "vue-awesome-swiper";
import "swiper/css/swiper.css";

export default {
  name: "Slider",
  components: {
    Swiper,
    SwiperSlide
  },
  directives: {
    swiper: directive
  },
  props: ["animals"],
  computed: {
    swiper() {
      return this.$refs.animalSlider.$swiper;
    }
  },
  methods: {
    playSound: function(animal) {
      const animalSound = document.querySelector(
        `audio[data-animal="${animal}"]`
      );
      animalSound.currentTime = 0;
      animalSound.play();
    },
    handleSlideChange: function() {
      this.playSound(this.swiper.realIndex ? this.swiper.realIndex : 0);
    }
  },
  data() {
    return {
      swiperOptions: {
        loop: true,
        grabCursor: true
      }
    };
  }
};
</script>

<style lang="scss" scoped>
img {
  height: 90vh;
  display: block;
  width: 100%;
}
</style>
