<template lang="html">
  <div class="activity-inner-container">
    <div class="card-container">
        <div class="inner" :style="{'background-image': 'url(' + imageSource + ')'}">
        </div>
        <div class="text-container">
            <h2 class="activity-title">
                {{title}}
            </h2>
            <p class="activity-time">
                {{time}}
            </p>
            <h3 class="activity-description">
                {{description}}
            </h3>
        </div>
        <div class="button-container">
            <a class="more-button" :href="link">查看更多</a>
            <a class="status-button" v-if="status" :href="link">我要報名</a>
            <div class="status-button close-status" v-if="!status">活動結束</div>
        </div>
    </div>
  </div>

</template>

<script>
  export default {
    data () {
      return {
        // imageSource: '../../src/assets/images/activity-demo.png',
        // imageSource: 'https://i.imgur.com/JR3ewe9.png',
        // title: '掰不完的夏天_迷你聚',
        // time: '2017-09-10  PM 1:30 - 5:30',
        // description: '好熱，一個未完成待續的夏天。我們都背著一個偉大的目標前進著。來吧！按下參加...',
        // status: 0
      }
    },
    props: {
        imageSource: {
            type: String,
            default: "https://i.imgur.com/JR3ewe9.png",
        },
        title: {
            type: String,
            default: "掰不完的夏天_迷你聚",
        },
        time: {
            type: String,
            default: "2017-09-10  PM 1:30 - 5:30",
        },
        description: {
            type: String,
            default: "好熱，一個未完成待續的夏天。我們都背著一個偉大的目標前進著。來吧！按下參加...",
        },
        status: {
            type: Boolean,
            default: false,
        },
        link: {
            type: String,
            default: "https://www.facebook.com/events/123586401630141/",
        }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
    @import '~styles/main.sass'

    .inner
        height: 160px
        background-size: cover
        background-position: center
        width: 100%
        border-top-right-radius: 12px
        border-top-left-radius: 12px
        @include pc-width
            height: 220px

    .card-container
        height: 100%
        width: 100%

    .activity-inner-container 
        height: 100%
        width: 100%
        border-radius: 12px
        overflow: hidden


    .text-container
        padding: 8px 16px
        @include pc-width
            padding: 16px 32px
        .activity-title
            width: 100%
            font-size: 20px
            font-weight: 700
            text-align: left
            margin-bottom: 0px
            margin-left: 0px
            @include pc-width
                font-size: 24px
                margin-bottom: 4px

        .activity-time
            color: $text-color-gray-super-light
            font-size: 9px
            font-weight: 400
            margin-top: 0px
            margin-bottom: 0px

        .activity-description
            margin-top: 8px

    .button-container
        position: absolute
        width: 100%
        padding: 4px 16px
        box-sizing: border-box
        bottom: 16px
        @include pc-width
            padding: 8px 32px
        .more-button
            color: $text-color-gray
            padding-top: 4px
            padding-bottom: 4px
            padding-left: 8px
            padding-right: 8px
            display: inline-block
            border-radius: 4px
            border: 1px $text-color-gray-light solid
            text-decoration: none
            transition-duration: 0.2s
            font-size: 16px
            @include pc-width
                padding-top: 8px
                padding-bottom: 8px
                padding-left: 16px
                padding-right: 16px
            &:hover
                color: white
                background: $text-color-gray-light


        .status-button
            padding-top: 4px
            padding-bottom: 4px
            padding-left: 8px
            padding-right: 8px
            background: $default-background-green-color
            display: inline-block
            border-radius: 4px
            float: right
            // cursor: pointer
            text-decoration: none
            transition-duration: 0.2s
            font-size: 16px
            @include pc-width
                padding-top: 8px
                padding-bottom: 8px
                padding-left: 16px
                padding-right: 16px
            &:hover
                background: $default-background-dark-green-color

        .close-status
            background: $default-background-gray-color-2
            cursor: default
            &:hover
                background: $default-background-gray-color-2


</style>