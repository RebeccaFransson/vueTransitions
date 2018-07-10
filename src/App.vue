<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Fade to Home</router-link>
    </div>
      <div id="nav">
      <router-link to="/parent">Slider Home</router-link> |
      <router-link to="/parent/about">Slider About</router-link>
    </div>
    <transition name="fade" mode="out-in">
      <router-view class="view"></router-view>
    </transition>
  </div>
</template>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
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
</style>
