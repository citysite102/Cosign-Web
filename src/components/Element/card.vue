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
            <div class="more-button">查看更多</div>
            <div class="status-button">我要報名</div>
        </div>
    </div>
  </div>

</template>

<script>
  export default {
    data () {
      return {
        imageSource: '../../src/assets/images/activity-demo.png',
        title: '掰不完的夏天_迷你聚',
        time: '2017-09-10  PM 1:30 - 5:30',
        description: '好熱，一個未完成待續的夏天。我們都背著一個偉大的目標前進著。來吧！按下參加...',
        status: 0
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
    @import '~styles/main.sass'

    .inner
        height: 280px
        width: 100%
        border-top-right-radius: 12px
        border-top-left-radius: 12px

    .card-container
        height: 100%
        width: 100%

    .activity-inner-container 
        height: 100%
        width: 100%
        border-radius: 12px
        overflow: hidden


    .text-container
        padding: 16px 32px
        .activity-title
            font-size: 28px
            font-weight: 700
            text-align: left
            margin-bottom: 4px

        .activity-time
            color: $text-color-gray-super-light
            font-size: 9px
            font-weight: 400

        .activity-description
            font-size: 20px
            margin-top: 16px

    .button-container
        padding: 8px 32px

        .more-button
            color: $text-color-gray
            padding-top: 8px
            padding-bottom: 8px
            padding-left: 16px
            padding-right: 16px
            display: inline-block
            border-radius: 4px
            border: 1px $text-color-gray-light solid

        .status-button
            padding-top: 8px
            padding-bottom: 8px
            padding-left: 16px
            padding-right: 16px
            background: $default-background-green-color
            display: inline-block
            border-radius: 4px
            float: right

</style>