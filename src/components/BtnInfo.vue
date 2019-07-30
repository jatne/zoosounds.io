<template>
  <button type="button" v-on:click="toggleInfo">
    <span v-show="isActive">made with</span> ❤️
    <span v-show="isActive">for Hania</span>
  </button>
</template>

<script>
export default {
  name: "BtnInfo",
  data() {
    return {
      isActive: false
    };
  },
  methods: {
    toggleInfo() {
      this.isActive = !this.isActive;
    }
  }
};
</script>
