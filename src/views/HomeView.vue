<template>
  <div class="home">
    <p class="home_title">X's and O's</p>
    <p class="home_head">It's time to show!</p>
    <div class="home_wrap">
      <img class="home_image" src="../assets/tic-tac-toe.svg" />
    </div>
    <router-link :to="{name: 'game'}">
      <button class="home_play">Start a new game!</button>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'HomeView',
}
</script>
<style lang="stylus" scoped>
@import '../styles/home.styl'
</style>
