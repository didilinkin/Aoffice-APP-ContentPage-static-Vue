<template>
    <div id="content">
        <img :src="banner" />
        <textContent />
    </div>
</template>

<script>
import textContent from './textcontent.vue'
export default {
    name: 'nav',
    data () {
        return {
            banner: require('../assets/picJiashengshidai@2x.png')
        }
    },
    components: { textContent }
}
</script>

<style lang="sass?indentedSyntax">
@import '../sass/mixin.sass'
#content
    margin-top: ((103.5px-32.5px-25px)/37.5px)*1rem
    >img
        width: 100%
        @extend %block
        +REM(height,120px)
</style>
