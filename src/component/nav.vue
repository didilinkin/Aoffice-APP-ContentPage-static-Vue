<template>
    <div id="nav">
        <span class="return" v-on:click="returnBtn">
            <img :src="returnImg">
        </span>
        <h1>{{msg}}</h1>
        <span class="iconDialogue" v-on:click="dialogue">
            <img :src="iconDialogueImg">
        </span>
    </div>
</template>

<script>
export default {
    name: 'nav',
    data () {
        return {
            msg: '办公装修',
            returnImg: require('../assets/return@2x.png'),
            iconDialogueImg: require('../assets/iconDialogue@2x.png'),
            returnBtn: function () { alert('returnBtn') },
            dialogue: function(){ alert('dialogue') }
        }
    },
}
</script>

<style lang="sass?indentedSyntax">
@import '../sass/mixin.sass'
#nav
    position: relative
    extend %flexCenter
    text-align: center
    +REM(margin-top,20px)
    /*+REM(margin-bottom,17px)*/
    +REM(height,25px)
    span.return
        position: absolute
        left: 0
        img
            +REM(width,19.5px)
    span.iconDialogue
        position: absolute
        right: 0
        img
            +REM(width,19.5px)
    h1
        @extend %dib
        +REM(font-size,16px)
        color: #FFF
</style>
