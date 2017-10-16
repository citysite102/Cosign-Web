<template lang="html">
    <div class="footer">
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
                        <li class="footer-facebook">
                        </li>
                    </ul>
                    <div class="footer-copyright">
                        Cosign© 2017 All Right Reserved.
                    </div>
                </el-col>
            </el-row>
    </div>

</template>

<script>
  export default {
    data () {
      return {
        message: 'Card',
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="sass">
    @import '~styles/main.sass';

    .footer
        background-color: $default-footer-color
        height: 100%
        padding: 40px
        text-align: center  // 注意，ul, li 要用text-aligh 來放到中間中

        .footer-copyright
            margin-top: 8px
            font-size: 16px
            transform: translateX(-16px)

        .link-container
            vertical-align: bottom
            display: inline-block
            top: 50%
            padding: 0px

            .link-item
                list-style: none
                display: inline-block
                width: auto
                margin-right: 60px
                a
                    font-size: 20px
                    font-weight: 400
                    color: white
                    text-decoration: none
                    transition-duration: 0.1s

            .footer-facebook
                width: 28px
                height: 28px
                list-style: none
                display: inline-block
                transform: translateY(6px)
                background-size: cover
                background-position: center
                background-image: url('~assets/images/icon-facebook.png')


</style>