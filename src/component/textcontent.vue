<template>
    <div id="textcontent">
        <!-- 关于我们 -->
        <aboutUs class="modules">
            <h2><b>关于我们</b></h2>
            <string />
            <!-- 关于我们-文字内容 -->
            <aboutus-content></aboutus-content>
        </aboutUs>

        <!-- 装修套餐 -->
        <decorationSet class="modules">
            <h2><b>装修套餐</b></h2>
            <string />
            <!-- 套餐列表 -->
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
        </decorationSet>

        <!-- 装修流程 -->
        <decorationFlow class="modules">
            <h2><b>装修流程</b></h2>
            <string />
            <img :src="decorationFlow" />
        </decorationFlow>

        <!-- 使用说明 -->
        <explain class="modules">
            <h2><b>使用说明</b></h2>
            <string />
            <ul>
                <li>
                    <NO class="explainFont">1、</NO>
                    <p class="explainFont">您可直接拨打我司电话，提出您的装修请求</p>
                </li>
                <li>
                    <NO class="explainFont">2、</NO>
                    <p class="explainFont">我们会尽快约定为你约定专家，实地并给予您专业的装修建议</p>
                </li>
                <li class="explainFont">
                    <NO class="explainFont">3、</NO>
                    <p class="explainFont">最终解释权归A+office所有</p>
                </li>
            </ul>
        </explain>
    </div>
</template>

<script>
import aboutuscontent from './aboutus-content.vue'

export default {
    name: 'textcontent',
    data () {
        return {
            discount: '95',
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
            ],
            decorationFlow: require('../assets/decorationFlow.png')
        }
    },
    components: {
        // <aboutus-content> 将只在父模板可用
        'aboutus-content': aboutuscontent
    }
};




</script>
<style lang="sass?indentedSyntax">
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

#textcontent
    +REM(padding-top,16.5px)
    +REM(padding-right,16px)
    +REM(margin-bottom,15.5px)
    +REM(padding-left,16px)
    +boxShadow(0px,2px,20px,rgba(143,153,175,.5))
    /* 4个文字内容模块公用样式 */
    .modules
        display: block
        +REM(padding-bottom,25px)
        h2
            @extend %title-font
        /* 实线 */
        string
            display: block
            +REM(height,1px)
            border-top: 1px solid $title-color
            +REM(border-bottom-width,1px)
            +REM(margin-top,14.8px)
            +REM(margin-bottom,14.8px)
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

/* 装修流程-模块 */
decorationFlow img
    width: 100%

/* 使用说明-模块 */
explain li
    overflow: hidden
    display: block
    NO
        @extend %dib
        float: left
        +REM(width,24px)
    p
        @extend %dib
        float: right
        +REM(width,311px-25px)
    /* 说明文字-字体样式 */
    .explainFont
        +REM(font-size,14px)
        +REM(line-height,23px)
        color: $text-color
</style>
