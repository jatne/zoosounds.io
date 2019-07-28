<template>
  <button type="button" v-on:click="toggleInfo">
    <span v-if="isActive">made with</span> ❤️
    <span v-if="isActive">for Hania</span>
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
