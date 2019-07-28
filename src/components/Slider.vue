<template>
  <carousel :paginationEnabled="false" :perPage="1">
    <slide v-for="(animal, index) in animals" v-bind:key="index">
      <div v-on:click="playSound(animal.name)">
        <img :src="require(`@/assets/zoo/images/${animal.image}`)" v-bind:alt="animal.name" />
        <audio
          v-bind:src="require(`@/assets/zoo/sounds/${animal.sound}`)"
          v-bind:data-animal="animal.name"
        ></audio>
      </div>
    </slide>
  </carousel>
</template>
<script>
import { Carousel, Slide } from "vue-carousel";

export default {
  name: "Slider",
  components: {
    Carousel,
    Slide
  },
  data() {
    return {
      animals: [
        {
          name: "Duck",
          image: "duck.svg",
          sound: "duck.mp3"
        },
        {
          name: "Cow",
          image: "cow.svg",
          sound: "cow.mp3"
        },
        {
          name: "Crow",
          image: "crow.svg",
          sound: "crow.mp3"
        },
        {
          name: "Dog",
          image: "dog.svg",
          sound: "dog.mp3"
        },
        {
          name: "Elephant",
          image: "elephant.svg",
          sound: "elephant.mp3"
        },
        {
          name: "Horse",
          image: "horse.svg",
          sound: "horse.mp3"
        },
        {
          name: "Owl",
          image: "owl.svg",
          sound: "owl.mp3"
        },
        {
          name: "Pig",
          image: "pig.svg",
          sound: "pig.mp3"
        },
        {
          name: "Rooster",
          image: "rooster.svg",
          sound: "rooster.mp3"
        },
        {
          name: "Sheep",
          image: "sheep.svg",
          sound: "sheep.mp3"
        }
      ]
    };
  },
  methods: {
    playSound: function(animal) {
      const animalSound = document.querySelector(
        `audio[data-animal=${animal}]`
      );
      animalSound.currentTime = 0;
      animalSound.play();
    }
  }
};
</script>

<style lang="scss" scoped>
img {
  max-height: 100vh;
}
</style>
