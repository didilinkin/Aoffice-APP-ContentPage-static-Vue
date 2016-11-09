<template>
    <div id="nav">
        <span class="return">
            <img :src="returnBtn">
        </span>
        <h1>{{msg}}</h1>
        <span class="iconDialogue">
            <img :src="iconDialogueBtn">
        </span>
    </div>
</template>

<script>
export default {
    name: 'nav',
    data () {
        return {
            msg: '办公装修',
            returnBtn: require('../assets/return@2x.png'),
            iconDialogueBtn: require('../assets/iconDialogue@2x.png')
        }
    }
}
</script>

<style lang="sass?indentedSyntax">
@import '../sass/mixin.sass'
#nav
    position: relative
    extend %flexCenter
    text-align: center
    +REM(height,25px)
    span.return
        position: absolute
        left: 0
    span.iconDialogue
        position: absolute
        right: 0
    h1
        @extend %dib
        +REM(font-size,16px)
        color: #FFF
</style>
