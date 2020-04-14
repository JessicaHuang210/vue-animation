<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link>|
      <router-link to="/about">About</router-link>
    </div>
    <transition name="slide-in">
      <router-view />
    </transition>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}

.slide-in-enter {
  /* transform: translateX(10px); */
  opacity: 0;
}
.slide-in-enter-active {
  transition: 0.5s ease;
}
.slide-in-leave-to {
  opacity: 0;
}

.slide-up-enter {
  transform: translateY(10px);
  opacity: 0;
}
.slide-up-enter-active {
  transition: 0.2s ease;
}
.slide-up-move {
  transition: transform 0.5s ease;
}
</style>
