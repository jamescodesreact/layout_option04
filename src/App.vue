<template>
  <div class="main-container">
    <NavBar />
    <router-view />
  </div>
</template>

<style lang="scss">
@import "reset-css";

.main-container {
  display: flex;
  flex-direction: column;
  height: 100%;
  width: 100%;
  min-height: 100%;
  padding: 0px;
  margin: 0px;
}

#app {
  color: #2c3e50;
  min-height: 100%;
  min-width: 100%;
}

html,
body {
  height: 100%;
  margin: 0;
  padding: 0;
}

body {
  font-family: "Segoe UI", sans-serif;
}

nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
<script setup lang="ts">
import NavBar from "@/components/NavBar.vue";
import "@progress/kendo-theme-fluent/dist/all.css";
</script>
