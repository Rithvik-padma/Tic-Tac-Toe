<template>
    <div class="gameView_game">
        <button class="gameView_box" v-for="(square, index) in squares" :key="index">
            <i v-if="square == 'x'" class="tic-item"></i>
            <i v-else-if="square == 'o'" class="tic-item"></i>
        </button>
    </div>
</template>

<script>
    export default {
        name: 'TicTacToe',
        data(){
            return {
                
            }
        },
        props: {
            squares: Array,
            player: String
        }    
    }
</script>

<style lang="stylus" scoped>
    @import '../styles/game.styl'
</style>