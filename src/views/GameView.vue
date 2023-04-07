<template>
  <div class="gameView">
    <GameHeader :header="header"/>
    <TicTacToe :squares="squares" :player="player" @updateSquarePlayer="updateSquarePlayer"/>
    <router-link :to="{name: 'game'}">
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
    },
    methods:{
      updateSquarePlayer(squares){
        this.squares = squares
        this.player = this.player == 'x' ? 'o' : 'x'
        this.header = `Player ${this.player.toUpperCase()}'s turn`
      },
    },
  }
</script>

<style lang="stylus" scoped>
  @import '../styles/game.styl'
</style>
