<template>
  <div class="home">
    <h1>This is an home page</h1>
    <input v-model="newList" />
    <button @click="handleAddClick">add</button>
    <button @click="handleSortClick">sort</button>
    <transition-group appear name="slide-up" tag="ul">
      <li :key="i" v-for="i in list">{{ i }}</li>
    </transition-group>

    <transition
      appear=""
      :css="false"
      @before-enter="beforeEnter"
      @enter="enter"
    >
      <div class="box"></div>
    </transition>
  </div>
</template>

<script>
// @ is an alias to /src
import gsap from "gsap";
export default {
  name: "Home",
  data() {
    return {
      newList: "",
      list: ["hambrgur", "books", "sunday"]
    };
  },
  methods: {
    handleAddClick() {
      this.list.push(this.newList);
      this.newList = "";
    },
    handleSortClick() {
      this.list.sort();
    },
    // gsap -----
    beforeEnter(el) {
      el.style.opacity = 0;
      el.style.transform = "scale(0,0)";
    },
    enter(el, done) {
      gsap.to(el, {
        duration: 1,
        opacity: 1,
        scale: 1,
        ease: "bounce.out",
        onComplete: done
      });
    }
  }
};
</script>
<style lang="scss" scoped>
.box {
  width: 100px;
  height: 100px;
  background-color: red;
  margin: auto;
}
</style>
