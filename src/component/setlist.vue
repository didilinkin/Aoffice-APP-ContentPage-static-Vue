<template>
    <ul id="setlist">
        <li>
            <img :src="setList[0].img"/>
            <listTitle class="font"><b>{{ setList[0].title }}</b></listTitle>
            <listContent class="font">{{ setList[0].content }}</listContent>
        </li>
        <dashed />
        <li>
            <img :src="setList[1].img"/>
            <listTitle class="font"><b>{{ setList[1].title }}</b></listTitle>
            <listContent class="font">{{ setList[1].content }}</listContent>
        </li>
        <dashed />
        <li>
            <img :src="setList[2].img"/>
            <listTitle class="font"><b>{{ setList[2].title }}</b></listTitle>
            <listContent class="font">{{ setList[2].content }}</listContent>
        </li>
        <dashed />
        <li>
            <img :src="setList[3].img"/>
            <listTitle class="font"><b>{{ setList[3].title }}</b></listTitle>
            <listContent class="font">{{ setList[3].content }}</listContent>
        </li>
        <dashed />
        <li>
            <img :src="setList[4].img"/>
            <listTitle class="font"><b>{{ setList[4].title }}</b></listTitle>
            <listContent class="font">{{ setList[4].content }}</listContent>
        </li>
        <dashed />
    </ul>
</template>

<script>
export default {
    name: 'textcontent',
    data () {
        return {
            setList: [
                {
                    img: require('../assets/icoFreemeasure@2x.png'),
                    title: '免费测量',
                    content: '免费为办公室提供分析、测量、报价'
                },
                {
                    img: require('../assets/icoFreedesign@2x.png'),
                    title: '免费设计',
                    content: '正式合作后，免费设计后期保修服务'
                },
                {
                    img: require('../assets/icoChoose@2x.png'),
                    title: '按需选择',
                    content: '可选择单项装修服务(隔断、走线等)或是整套装修服务'
                },
                {
                    img: require('../assets/icoService@2x.png'),
                    title: '服务细项',
                    content: '服务细项包括走线、刮泥、吊顶、水电、地砖、隔断等'
                },
                {
                    img: require('../assets/icoAdvice@2x.png'),
                    title: '专业建议',
                    content: '可根据客户需求、实地考察并给予专业的装修建议'
                }
            ]
        }
    }
};
</script>

<style lang="sass?indentedSyntax" scoped>
@import '../sass/mixin.sass'

/* 模块内通用变量 */
$title-size: 15px
$title-color: rgb(115,125,145)
%title-font
    +REM(font-size,15px)
    color: rgb(115,125,145)
$text-size: 14px
$text-color: rgb(143,153,175)
%text-font
    +REM(font-size,14px)
    color: rgb(143,153,175)
$dashed-color: rgb(187,197,219)

/* 套餐列表-模块 */
=setlistAuto($width)
    float: left
    +REM(width,$width)
    height: 100%
#setlist li
    +REM(height,42px)
    img
        +setlistAuto(42px)
    listTitle
        display: flex
        align-items: center
        +setlistAuto(126.5px-10.5px)
        +REM(padding-left,10.5px)
    /* 标题字体样式 */
    listTitle.font
        @extend %title-font
        +REM(line-height,21px)
    listContent
        @extend %flexCenter
        +setlistAuto(142.5px)
    /* 列表内容字体样式 */
    listContent.font
        +REM(font-size,12px)
        +REM(line-height,18px)
        color: $text-color
/* 虚线 */
dashed
    display: block
    +REM(height,1px)
    border-top: 1px dashed $dashed-color
    +REM(border-bottom-width,1px)
    +REM(margin-top,17px)
    +REM(margin-bottom,17px)
dashed:last-child
    +REM(margin-bottom,0px)
</style>