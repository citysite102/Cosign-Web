<template lang="html">
    <div>
        <div class="header">
            <el-row :gutter="16">
                <!-- <el-col :span="10" :offset="1"> -->
                    <!-- <div class="menu"></div> -->
                    <!-- <menuButton></menuButton> -->
                <!-- </el-col> -->
                <el-col :span="20" :offset="2">
                    <ul class="link-container">
                        <li class="link-item">
                            <a class="link" href="#" v-scroll-to="'.section-about'">關於我們
                            </a>
                        </li>
                        <li class="link-item">
                            <a class="link" href="#" v-scroll-to="'.section-member'">成員列表
                            </a>
                        </li>
                        <li class="link-item">
                            <a class="link" href="#" v-scroll-to="'.section-activity'">活動資訊
                            </a>
                        </li>
                    </ul>
                </el-col>
            </el-row>
        </div>
    </div>
</template>

<script>
    import MenuButton from './menuButton.vue';
    import ScrollTo from 'vue-scrollto';

    export default {
        data () {
            return {
                message: 'header',
            }
        },
        components: {
            MenuButton
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
  
    @import '~styles/main.sass'

    .header
        background-color: clear
        width: 100%
        z-index: 2
        padding-top: 120px

    .menu
        +size(40px, 40px)
        background-color: gray
        display: inline-block
        top: 50%
        transform: translateY(-50%)
        margin-left: 60px

    .link-container
        display: inline-block
        height: 100%
        margin: 0px
        float: right
        text-align: right

    .link-item
        list-style: none
        display: inline-block
        width: auto
        top: 50%
        transform: translateY(-50%)
        margin-right: 60px
        font-size: 22px

        a
            font-size: 22px
            text-decoration: none
            transition-duration: 0.1s

    .link
        color: $text-color-normal
        &:hover
            color: $text-color-normal
            &:after
                transform: scale3d(1, 1, 1)

        &:after
            content: ''
            position: absolute
            background: $text-color-normal
            transition: transform 0.2s
            transition-timing-function: cubic-bezier(1, 0.68, 0.16, 0.9)
            bottom: -6px
            left: -6px
            height: 3px
            width: calc(100% + 12px)
            transform: scale3d(0, 1, 1)
            transform-origin: 0% 50%


        
</style>