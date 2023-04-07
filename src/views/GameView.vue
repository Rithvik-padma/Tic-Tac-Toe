<template>
  <div class="gameView">
    <GameHeader :header="header"/>
    <TicTacToe :class="{'disabled' : gameDisabled}" :squares="squares" :player="player" @updateSquarePlayer="updateSquarePlayer" @updateWinner="updateWinner"/>
    <router-link :to="{name: 'game'}">
      <button v-if="complete" class="gameView_reset">Reset</button>
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
        complete: false,
        winCheck: [
                    [0,1,2],
                    [3,4,5],
                    [6,7,8],
                    [0,3,6],
                    [1,4,7],
                    [2,5,8],
                    [0,4,8],
                    [2,4,6]
                ],
        gameDisabled: false
      }
    },
    methods:{
      winnerCheck(){
        for(let i = 0; i < this.winCheck.length; i++){
          const [a,b,c] = this.winCheck[i]
          const squares = this.squares
          if(squares[a] && squares[a] === squares[b] && squares[a] === squares[c]){
            this.gameDisabled = true
            this.updateWinner(squares[a])
            break
          }
        }
      },
      updateSquarePlayer(squares){
        this.squares = squares
        this.player = this.player == 'x' ? 'o' : 'x'
        this.header = `Player ${this.player.toUpperCase()}'s turn`
        this.winnerCheck()
      },
      updateWinner(winner){
        this.header = `Player ${winner.toUpperCase()} is the winner!`
        this.complete = true
      },
    },
  }
</script>

<style lang="stylus" scoped>
  @import '../styles/game.styl'
</style>
