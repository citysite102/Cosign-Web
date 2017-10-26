<template lang="html">
  <div class="member-inner-container">
    <div class="card-container-member">
        <div class="inner" :style="{'background-image': 'url(' + imageSource + ')'}">
        </div>
        <div class="profile-container">
            <h2 class="member-name">
                {{name}}
            </h2>
            <p class="member-job">
                {{job}}
            </p>
            <div>
                <ul class="link-container">
                    <li v-if="showGithub" class="link-icon icon-github"><a :href="github"></a></li>
                    <li v-if="showMedium" class="link-icon icon-medium"><a :href="medium"></a></li>
                    <li v-if="showDribbble" class="link-icon icon-dribbble"><a :href="dribbble"></a></li>
                    <li v-if="showBehance" class="link-icon icon-behance"><a :href="behance"></a></li>
                </ul>
            </div>
            <div class="skill-container">
                
            </div>
            <h3 class="member-description">
                {{description}}
            </h3>
            <div class="button-container-member">
                <a class="friend-button" :href="facebook">交個朋友</a>
            </div>
        </div>
    </div>
  </div>

</template>

<script>
  export default {
    data () {
      return {
      }
    },
    props: {
        showGithub: {
            type: Boolean,
            default: true,
        }, 
        github: {
            type: String,
            default: "https://github.com/citysite102",
        },
        showMedium: {
            type: Boolean,
            default: true,
        },
        medium: {
            type: String,
            default: "https://medium.com/@citysite1025",
        },
        showDribbble: {
            type: Boolean,
            default: false,
        },
        dribbble: {
            type: String,
            default: "https://dribbble.com",
        },
        showBehance: {
            type: Boolean,
            default: false,
        },
        behance: {
            type: String,
            default: "https://www.behance.net",
        },
        imageSource: {
            type: String,
            default: "https://i.imgur.com/tj5Xgfa.jpg",
        },
        name: {
            type: String,
            default: "Samuel",
        },
        job: {
            type: String,
            default: "軟體工程師 / 介面設計師",
        },
        description: {
            type: String,
            default: "熱愛美好的事物，設計跟攝影。如果有任何有趣或者充滿挑戰的想法歡迎一起聊聊。",
        },
        facebook: {
            type: String,
            default: "https://www.facebook.com/citysite1025",
        }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
    @import '~styles/main.sass'

    .inner
        height: 90px
        width: 90px
        margin-left: auto
        margin-right: auto
        margin-top: 24px
        border-radius: 50%
        border: solid 1px $default-background-gray-color
        background-size: cover
        background-position: center
        @include pc-width
            height: 120px
            width: 120px
            margin-top: 32px

    .card-container-member
        height: 100%
        width: 100%

    .member-inner-container
        height: 100%
        width: 100%
        border-radius: 12px
        overflow: hidden
        


    .profile-container
        padding: 16px 32px

        .member-name
            text-align: center
            font-size: 20px
            font-weight: 700
            margin-bottom: 0px
            @include pc-width
                font-size: 28px
                margin-bottom: 4px

        .member-job
            color: $text-color-gray-super-light
            font-size: 12px
            text-align: center
            font-weight: 400
            margin-top: 0px
            @include pc-width
                margin-top: 4px
                font-size: 14px

        .member-description
            // font-size: 20px
            font-size: 14px
            margin-top: 16px
            text-align: center
            @include pc-width
                font-size: 16px
                line-height: 26px


        .link-container
            display: flex
            justify-content: center
            padding-left: 20px
            padding-right: 20px
            margin-top: 8px
            margin-bottom: 8px
            @include pc-width
                margin-top: 16px
                margin-bottom: 16px
            .link-icon
                list-style: none
                width: 26px
                height: 26px
                margin-left: 4px
                margin-right: 4px
                border-radius: 50%
                background-size: cover
                opacity: 0.7
                transition-duration: 0.2s
                cursor: pointer
                @include pc-width
                    width: 32px
                    height: 32px
                    margin-left: 6px
                    margin-right: 6px
                &:hover
                    opacity: 1.0
                a
                    display: block
                    width: 100%
                    height: 100%
            .icon-github
                background-image: url('~assets/images/icon-github.png')
            .icon-behance
                background-image: url('~assets/images/icon-behance.png')
            .icon-dribbble
                background-image: url('~assets/images/icon-dribbble.png')
            .icon-medium
                background-image: url('~assets/images/icon-medium.png')

        .button-container-member
            margin-top: 16px

            @include pc-width
                margin-top: 24px
            .friend-button
                color: $text-color-gray
                display: block
                padding-top: 6px
                padding-bottom: 6px
                padding-left: 8px
                padding-right: 8px
                border-radius: 4px
                font-size: 16px
                border: 1px $text-color-gray-light solid
                margin-left: auto
                margin-right: auto
                text-align: center
                width: 80px
                transition-duration: 0.2s
                text-decoration: none

                &:hover
                    color: $default-background-green-color
                    border: 1px $default-background-green-color solid


                @include pc-width
                    width: 100px
                    font-size: 20px
                    padding-top: 8px
                    padding-bottom: 8px
                    padding-left: 16px
                    padding-right: 16px


</style>