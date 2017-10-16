<template lang="html">
    <div class="feedback-inner-container">
        <div class="feedback-profile">
            <div v-if="showLeft" class="inner" :style="{'background-image': 'url(' + imageSource + ')'}">
            </div>
            <div v-if="showLeft" class="feedback-name">
                {{feedbackName}}
            </div>
        </div>
        <div class="feedback-content">
            <div class="feedback-text">
                {{feedbackContent}}
            </div>
        </div>
        <div class="feedback-profile">
            <div v-if="showRight" class="inner" :style="{'background-image': 'url(' + imageSource + ')'}">
            </div>
            <div v-if="showRight" class="feedback-name">
                {{feedbackName}}
            </div>
        </div>
    </div>

</template>

<script>
  export default {
    data () {
      return {
        // imageSource: '../../src/assets/images/sample-profile.jpg',
        imageSource: 'https://i.imgur.com/tj5Xgfa.jpg',
        feedbackName: 'Samuel',
        feedbackContent: '覺得不錯，但因為現在心裡有些想做的議題，不知道未來有沒有辦法讓這活動變成能認識更多想要做side project的朋友們，anyway 覺得是很棒的開始！',
      }
    },
    props: {
        showLeft: {
            type: Boolean,
            default: true,
        },
        showRight: {
            type: Boolean,
            default: false,
        }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
    @import '~styles/main.sass'


    .feedback-inner-container
        padding-top: 24px
        padding-bottom: 24px
        // border: solid 1px red
    //     height: 100%
    //     width: 100%

    .feedback-profile
        display: inline-block
        // position: absolute
        left: 0%    
        width: 15%
        vertical-align: top
        .inner
            height: 120px
            width: 120px
            margin-left: auto
            margin-right: auto
            border-radius: 50%
            border: solid 1px $default-background-gray-color
            background-size: cover
            background-position: center

        .feedback-name
            text-align: center
            font-size: 20px
            font-weight: 500
            margin-top: 16px
            margin-bottom: 16px
            color: $text-color-normal

    .feedback-content
        display: inline-block
        vertical-align: top
        border-radius: 12px
        box-sizing: border-box
        box-shadow: 0px 5px 15px RGBA(0,0,0,0.15)
        padding: 32px
        // height: 120px
        width: 68%

        .feedback-text
            color: $text-color-gray
            font-size: 20px
            line-height: 36px

</style>