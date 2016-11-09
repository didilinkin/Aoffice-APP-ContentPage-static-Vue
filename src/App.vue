<template>
    <div id="app">
        <Nav />
        <Content />
    </div>

</template>

<script>
import Nav from './component/nav.vue'
import Content from './component/content.vue'
export default {
    name: 'app',
    data () {
        return {
            msg: '办公装修'
        }
    },
    components: { Nav,Content }
}
</script>

<style lang="sass?indentedSyntax">
@import './sass/mixin.sass'
#app
    +REM(padding-top,32.5px)
    +REM(padding-left,16px)
    +REM(padding-right,16px)
    +REM(padding-bottom,48px)
    width: ((375px-(16px)*2))/37.5px*1rem
    background:
        image: url(./assets/bGSeviceBanner1@2x.png)
        size: 100% auto
        repeat: no-repeat
</style>
