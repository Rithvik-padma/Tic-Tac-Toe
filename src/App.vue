<template>
  <div id="app">
    <HomeView />
    <router-view/>
  </div>
</template>

<script>
 export default {
  name: 'App',
  components: ['HomeView'],
  data(){
    return {

    }
  }
 }
</script>
<style>

</style>
