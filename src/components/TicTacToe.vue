<template>
    <div class="gameView_game" >
        <button class="gameView_box" @click.once="addItem(index)" v-for="(square, index) in squares" :key="index">
            <span v-if="square == 'x'" class="tic-item x-square">x</span>
            <span v-else-if="square == 'o'" class="tic-item o-square" >o</span>
        </button>
    </div>
</template>

<script>
    export default {
        name: 'TicTacToe',
        props: {
            squares: Array,
            player: String,
        },   
        methods: {
            addItem(index){
                const squares = this.squares.slice()
                squares[index] = this.player
                this.$emit('updateSquarePlayer', squares)
            }
        },
    }
</script>

<style lang="stylus" scoped>
    @import '../styles/game.styl'
</style>