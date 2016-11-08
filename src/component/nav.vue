<template>
    <div id="nav">
        <span class="return">
            <img src="../assets/return@2x.png">
        </span>
        <h1>{{msg}}</h1>
        <span class="iconDialogue">
            <img src="../assets/iconDialogue@2x.png">
        </span>
    </div>
</template>

<script>
export default {
    name: 'nav',
    data () {
        return {
            msg: '办公装修'
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
