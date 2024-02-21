<template>
  <div class="navbar-container">
    <div>
      <img
        src="../assets/logo-sense.png"
        alt="Vue logo"
        height="80"
        style="margin-left: 20px"
      />
    </div>
    <nav>
      <router-link to="/">Layout One</router-link> |
      <router-link to="/layout-two">Layout Two</router-link> |
      <router-link to="/layout-three">Layout Three</router-link> |
      <router-link to="/layout-four">Layout Four</router-link>
    </nav>
  </div>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style scoped>
.navbar-container {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  padding-top: 5px;
  padding-bottom: 5px;
  height: 80px;
}
</style>
