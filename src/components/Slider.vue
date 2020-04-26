<template>
  <swiper ref="mySwiper" :options="swiperOptions">
    <swiper-slide v-for="(animal, index) in animals" v-bind:key="index">
      <div v-on:click="playSound(animal.name)">
        <img
          :src="require(`@/assets/zoo/images/${animal.image}`)"
          v-bind:alt="animal.name"
        />
        <audio
          v-bind:src="require(`@/assets/zoo/sounds/${animal.sound}`)"
          v-bind:data-animal="animal.name"
        ></audio>
      </div>
    </swiper-slide>
  </swiper>
</template>
<script>
import { Swiper, SwiperSlide, directive } from 'vue-awesome-swiper';
import 'swiper/css/swiper.css';

export default {
  name: 'Slider',
  components: {
    Swiper,
    SwiperSlide,
  },
  directives: {
    swiper: directive,
  },
  data() {
    return {
      animals: [
        {
          name: 'Duck',
          image: 'duck.svg',
          sound: 'duck.mp3',
        },
        {
          name: 'Cow',
          image: 'cow.svg',
          sound: 'cow.mp3',
        },
        {
          name: 'Crow',
          image: 'crow.svg',
          sound: 'crow.mp3',
        },
        {
          name: 'Dog',
          image: 'dog.svg',
          sound: 'dog.mp3',
        },
        {
          name: 'Elephant',
          image: 'elephant.svg',
          sound: 'elephant.mp3',
        },
        {
          name: 'Horse',
          image: 'horse.svg',
          sound: 'horse.mp3',
        },
        {
          name: 'Owl',
          image: 'owl.svg',
          sound: 'owl.mp3',
        },
        {
          name: 'Pig',
          image: 'pig.svg',
          sound: 'pig.mp3',
        },
        {
          name: 'Rooster',
          image: 'rooster.svg',
          sound: 'rooster.mp3',
        },
        {
          name: 'Sheep',
          image: 'sheep.svg',
          sound: 'sheep.mp3',
        },
      ],
    };
  },
  methods: {
    playSound: function(animal) {
      const animalSound = document.querySelector(
        `audio[data-animal=${animal}]`
      );
      animalSound.currentTime = 0;
      animalSound.play();
    },
  },
};
</script>

<style lang="scss" scoped>
img {
  height: 100vh;
  display: block;
  width: 100%;
}
</style>
