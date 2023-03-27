<template>
  <div class="gameView">
    <GameHeader :header="header"/>
    <TicTacToe :squares="squares" :player="player"/>
    <router-link :to="{name:GameView}">
      <button v-show="complete" class="gameView_reset">Reset</button>
    </router-link>
  </div>
</template>

<script>
import GameHeader from '../components/GameHeader.vue'
import TicTacToe from '../components/TicTacToe.vue'

  export default {
    name: 'GameView',
    components:{
      GameHeader,
      TicTacToe
    },
    data(){
      return {
        squares: ['','','','','','','','',''],
        header: "Player X's turn",
        player: "x",
        complete: true
      }
    }
  }
</script>

<style lang="stylus" scoped>
  @import '../styles/game.styl'
</style>
