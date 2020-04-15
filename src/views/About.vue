<template>
  <div class="about">
    <h1>This is an about page</h1>
    <div class="box--wrap">
      <div v-for="i in 5" :key="i" class="box--item"></div>
    </div>
  </div>
</template>
<script>
import gsap from "gsap";
export default {
  name: "About",
  mounted() {
    gsap.from(".box--item", {
      duration: 0.5,
      opacity: 0,
      scale: 0,
      y: 200,
      ease: "power1",
      stagger: {
        each: 0.1,
        from: "edges"
      }
    });
  }
};
</script>
<style lang="scss" scoped>
.box {
  &--wrap {
    display: flex;
    justify-content: space-around;
  }
  &--item {
    width: 100px;
    height: 100px;
    background-color: green;
  }
}
</style>
