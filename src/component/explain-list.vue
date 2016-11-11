<template>
    <ul id="explainList">
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
</template>

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