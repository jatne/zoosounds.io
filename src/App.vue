<template>
  <div id="app" v-bind:class="isInvertedColors ? 'is-inverted' : ''">
    <main>
      <Slider :animals="animals"></Slider>
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
  data() {
    return {
      isInvertedColors: false,
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
  components: {
    Slider,
    BtnInvertColors,
    BtnInfo
  }
};
</script>

<style lang="scss">
*,
*::before,
*::after {
  box-sizing: border-box;
}

html {
  font-size: 55%;

  @media screen and (min-width: 48rem) {
    font-size: 62.5%;
  }
}

html,
body {
  margin: 0;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
    "Helvetica Neue", Arial, "Noto Sans", sans-serif, "Apple Color Emoji",
    "Segoe UI Emoji", "Segoe UI Symbol", "Noto Color Emoji";
  font-size: 1.6rem;
  font-weight: 400;
  line-height: 1.5;
  color: #000;
  text-align: left;
  background-color: #fff;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#app {
  --theme: #000000;
  --theme-inverse: #ffffff;

  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 100%;
  height: 100vh;
  min-height: 30rem;
  padding: 1rem;
  background: var(--theme-inverse);
  color: var(--theme);
  transition: all 0.3s ease;

  &.is-inverted {
    --theme: #ffffff;
    --theme-inverse: #000000;
  }
}

main {
  display: flex;
  width: 100%;
  flex-grow: 1;
  align-items: center;
}

img {
  max-width: 100%;
  height: auto;

  .is-inverted & {
    filter: invert(1);
  }
}

button {
  display: inline-block;
  border: 2px solid var(--theme);
  background: var(--theme-inverse);
  color: var(--theme);
  outline: none;
  text-transform: uppercase;
  font-weight: bold;
  font-size: 1.25rem;
  border-radius: 4px;
  margin: 0;
  padding: 2px 8px;
  cursor: pointer;
  transition: all 0.3s ease;

  &:hover {
    background: var(--theme);
    color: var(--theme-inverse);
  }
}

footer {
  display: flex;
  width: 100%;
  justify-content: space-between;
  align-content: center;
  position: relative;
  z-index: 2;
}
</style>
