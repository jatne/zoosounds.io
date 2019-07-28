<template>
  <button v-on:click="invertColors">Invert colors</button>
</template>

<script>
export default {
  name: "BtnInvertColors",
  methods: {
    invertColors() {
      this.$parent.isInvertedColors = !this.$parent.isInvertedColors;
    }
  }
};
</script>
