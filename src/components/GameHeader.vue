<template>
    <div>
        <h1 class="gameView_title">{{ header }}</h1>
    </div>
</template>

<script>
    export default {
        name: 'GameHeader',
        data(){
            return {
            }
        },
        props: {
            header: String
        }
    }
</script>

<style lang="stylus" scoped>
    @import '../styles/game.styl'
</style>