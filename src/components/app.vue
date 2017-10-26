<template lang="html">
    <div>
        <div class="container">
            <transition appear appear-to-class="fade-enter-content"
                                    appear-active-class="fade-enter-active-headerbar">
                <headerBar v-if="!compact" :showAbout="true" :showWork="false"></headerBar>
            </transition>
            <!-- <transition name="slide-fade">
                <pageIndicator v-show="isPageIndicatorShow" class="page-control" :currentIndex="pageIndex"></pageIndicator>
            </transition> -->
            <section class="section-landing">
                <div id="particles"></div>
                <transition appear appear-to-class="fade-enter-content"
                                    appear-active-class="fade-enter-active-scroll">
                    <img class="landing-logo" src="../assets/images/cosign-logo.png"/>
                </transition>

                <!-- <svg width="480px" height="250px" viewBox="0 0 480 250" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
                    <path d="M461.176471,244.230769 C468.397948,244.230769 474.230769,238.458426 474.230769,231.371643 L474.230769,18.6283568 C474.230769,11.5404449 468.398686,5.76923077 461.176471,5.76923077 L18.8235294,5.76923077 C11.6001697,5.76923077 5.76923077,11.5397113 5.76923077,18.6283568 L5.76923077,231.371643 C5.76923077,238.459159 11.6009079,244.230769 18.8235294,244.230769 L461.176471,244.230769 Z" stroke="#231F20" stroke-width="11.5384615" fill="none" fill-rule="evenodd">
                    </path>
                </svg> -->
            </section>
            <section class="section-about">
                <h1>關於我們</h1>
                <h2>腦中總是浮現各種點子卻不知道該找誰合作，或該如何實現嗎？<br><br>在2017年的夏天，Cosign的夥伴們在不同場合的設計/工程講座活動中合作相識，除了驚豔於各自不同領域的才華與經歷之外，更在深聊後發現彼此熱愛分享的特質，與對跨界合作創業的熱忱。大家開始思考：也許能夠連結起不同故事、不同背景，但是理念相同的夥伴？<br><br>秉持著這樣的理念，這ㄧ群志同道合的夥伴成立了Cosign，一個跨領域的工程師設計師交流聚會，期待能透過「分享」「共同成長」的理念實踐，一起Co-Design！</h2>
                <div class="about-container">
                    <div class="about-item">
                        <img class="landing-logo" src="../assets/images/icon_com.png"/>
                        <h1>交流</h1>
                    </div>
                    <div class="about-item">
                        <img class="landing-logo-long" src="../assets/images/icon_de.png"/>
                        <h1>設計與開發</h1>
                    </div>
                    <div class="about-item">
                        <img class="landing-logo" src="../assets/images/icon_card.png"/>
                        <h1>桌遊</h1>
                    </div>
                </div>

            </section>
            <section class="section-member">
                <h1>Cosign 夥伴</h1>
                <h2>歡迎有著和我們一樣想法的夥伴加入 Cosign；再加入我們之前，我們誠摯地邀請你參與我們每個月的交流活動，聊聊大家的故事和目標，讓彼此更了解一些：）</h2>
                <div class="member-container">
                    <div class="swiper-button-prev" slot="button-prev"></div>
                    <swiper :options="swiperOption" ref="mySwiper">
                        <swiper-slide>
                            <transition name="fade-delay1" @after-enter="afterEnter">
                                <memberCard v-show="isMemberCardShow" class="member-card" v-bind:class="{ cardAnimation:isActivityCardFinishShow}"></memberCard>
                            </transition>
                        </swiper-slide>
                        <swiper-slide>
                            <transition name="fade-delay2" @after-enter="afterEnter">
                                <memberCard v-show="isMemberCardShow" class="member-card" v-bind:class="{ cardAnimation:isActivityCardFinishShow}" imageSource="https://i.imgur.com/iVIjNNr.jpg" name="Money" job="互動設計師" description="熱愛設計與閱讀，創作靈感常來自於日常生活中那些奇妙片刻。
研究所時期邂逅了UX，踏上一段又一段使用者旅程，試著為世界創造一些美好。" facebook="https://www.facebook.com/profile.php?id=100010171684035"></memberCard>
                            </transition>
                        </swiper-slide>
                        <swiper-slide>
                            <transition name="fade-delay3" @after-enter="afterEnter">
                                <memberCard v-show="isMemberCardShow" class="member-card" v-bind:class="{ cardAnimation:isActivityCardFinishShow}" imageSource="https://i.imgur.com/smJexCd.jpg" name="Gwynne" job="互動設計師" description="畢業於SCAD藝術設計學院，喜愛探索美好，擅長以使用者經驗的層面去設計互動體驗的本質，時常參與讀書會，長期關注介面設計與心理學。" facebook="https://www.facebook.com/GwynneLL"></memberCard>
                            </transition>
                        </swiper-slide>
                        <swiper-slide>
                            <transition name="fade-delay2" @after-enter="afterEnter">
                                <memberCard v-show="isMemberCardShow" class="member-card" v-bind:class="{ cardAnimation:isActivityCardFinishShow}"></memberCard>
                            </transition>
                        </swiper-slide>
                        <div class="swiper-pagination" slot="pagination"></div>
                        <!-- <div class="swiper-button-prev" slot="button-prev"></div>
                        <div class="swiper-button-next" slot="button-next"></div> -->
                    </swiper>
                    <div class="swiper-button-next" slot="button-next"></div>
                </div>
                <transition name="fade-delay4">
                    <div v-show="isMemberCardShow" class="check-more">
                        <a href='https://www.facebook.com/groups/207617269772052/?ref=br_rs'>加入我們！</a>
                    </div>
                </transition>
            </section>
            <section class="section-activity">
                <h1>活動資訊</h1>
                <h2>從2017年9月開始，Cosign 開始定期舉辦交流活動。在活動中各自分享工作經驗、分享自己的專業，或者單純聚在一起聊天、玩桌遊、煮火鍋；在交流會之外，我們也定期舉辦微型workshop，邀請民間高手帶著夥伴挑戰網頁開發、介面設計，目標是在共學的精神下讓夥伴們共同成長。</h2>
                <div class="activity-container">
                    <div class="swiper-button-prev" slot="button-prev"></div>
                    <swiper :options="swiperOption">
                        <swiper-slide>
                            <transition name="fade-delay2">
                                <card v-show="isActivityCardShow" class="activity-card" imageSource="https://i.imgur.com/oLTfsHm.jpg" title="霜降。還來不及跟秋天說聲嗨_迷你聚#3" description="轉眼間秋天就要結束，霜降是秋季的最後一個節氣；是時候該來一次霜降系列（牛豬雞羊）的火鍋交流聚會囉。" :status="true" link="https://www.facebook.com/events/1893827037598431/" v-bind:class="{ cardAnimation:isActivityCardFinishShow}"></card>
                            </transition>
                        </swiper-slide>
                        <swiper-slide>
                            <transition name="fade-delay1">
                                <card v-show="isActivityCardShow" class="activity-card" v-bind:class="{ cardAnimation:isActivityCardFinishShow}" title="掰不完的夏天_迷你聚#2"></card>
                            </transition>
                        </swiper-slide>
                        <swiper-slide>
                            <transition name="fade-delay3">
                                <card v-show="isActivityCardShow" class="activity-card" v-bind:class="{ cardAnimation:isActivityCardFinishShow}" title="掰不完的夏天_迷你聚#1"></card>
                            </transition>
                        </swiper-slide>
                    </swiper>
                    <div class="swiper-button-next" slot="button-next"></div>
                </div>
                <transition name="fade-delay4">
                    <div v-show="isActivityCardShow" class="check-more">
                        <a href='https://www.facebook.com/groups/207617269772052/?ref=br_rs'>查看更多活動資訊</a>
                    </div>
                </transition>
            </section>
            <section class="section-feedback">
                <h1>活動回饋</h1>
                <transition-group class="feedback-container" name="feedback-update" tag="p">
                    <div v-for="(item, index) in feedbackItems"
  v-bind:key="item" class="feedback-card-container">
                        <feedbackCard  class="feedback-card" :feedbackContent=feedbackContent[item] :showRight="shouldShowRight(index)" :showLeft="shouldShowLeft(index)"></feedbackCard>
                    </div>
                </transition-group>
                <div class="contact-container">
                    <div class="icon-hand">
                    </div>
                    <div class="join-text">
                        加入我們或者和我們聊聊
                    </div>
                    <div class="contact-email">
                        <a :href="'mailto:theCosignstudio@gmail.com'">theCosignstudio@gmail.com</a>
                    </div>
                </div>
            </section>
        </div>
        <footerBar></footerBar>
    </div>
</template>

<script>
    import Vue from 'vue';
    import HeaderBar from './Element/header.vue';
    import FooterBar from './Element/footer.vue';
    import PageIndicator from './Element/pageIndication.vue';
    import Card from './Element/card.vue';
    import MemberCard from './Element/member-card.vue';
    import FeedbackCard from './Element/feedback-card.vue';
    import ScrollTrigger from 'scrolltrigger-classes';
    import ScrollTo from 'vue-scrollto';
    import Rellax from 'rellax';
    // import particlesJS from '../assets/js/particles.min.js'
    import particles from 'particles.js'
    import particlesJson from '../assets/particle.json'

    // require('swiper/dist/css/swiper.css')

    // 用 import 也可以。
    var VueScrollTo = require('vue-scrollto');
    var VueAwesomeSwiper = require('vue-awesome-swiper')

    var scrollFunction;

    Vue.use(VueScrollTo, {
        container: "body",
        duration: 1000,
        easing: [0.14, 1.08, 0.31, 0.98],
        offset: -240,
        cancelable: true,
        onDone: false,
        onCancel: false,
        x: false,
        y: true
    });

    Vue.use(VueAwesomeSwiper);


    export default {
        data () {
            return {
                partialIndex: 0,
                currentFeedbackIndex: 3,
                feedbackItems: [0, 1, 2],
                feedbackContent: ["回饋1", 
                "回饋2 有很多的文字敘述喔！", 
                "回饋3", 
                "回饋4", 
                "回饋5", 
                "回饋6,回饋6,回饋6,回饋6,回饋6,回饋6,回饋6,回饋6也有很多的文字敘述喔！回饋6,回饋6,回饋6,回饋6,回饋6,回饋6,回饋6,回饋6也有很多的文字敘述喔！有很多的文字敘述喔！！", 
                "回饋7還有很多的文字敘述喔！回饋7還有很多的文字敘述喔！回饋7還有很多的文字敘述喔！回饋7還有很多的文字敘述喔！回饋7還有很多的文字敘述喔！", 
                "回饋8"],
                swiperOption: {
                    // pagination: '.swiper-pagination',
                    // paginationClickable: true,
                    slidesPerView: 3,
                    nextButton: '.swiper-button-next',
                    prevButton: '.swiper-button-prev',
                    spaceBetween: 0,
                    observer:true,
                    observeParents:true,
                },
                defaultTrue: true,
                isScrollHintShow: true,
                isMemberCardShow: false,
                isActivityCardShow: false,
                isActivityCardFinishShow: false,
                isFeedbackCardShow: false,
                isPageIndicatorShow: false,
                compact: false,
                pageIndex: 1,
                projectIndex: 0,
                projectTitles: ['Tickle', 'Kapi', 'Cosign'],
                projectTimes: ['2016.1-2017.1', '2016.2-2017.2', '2016.3-2017.3'],
                projectDescriptions: ['1Lorem ipsum dolor sit amet, consectetur adipisicing elit, Lorem ipsum dolor sit amet', '2Lorem ipsum dolor sit amet, consectetur adipisicing elit, Lorem ipsum dolor sit amet', '3Lorem ipsum dolor sit amet, consectetur adipisicing elit, Lorem ipsum dolor sit amet'],
                projectJobs: ['Engineer, UI Deisgn and Script','Cofounder, iOS developement','Cofunder, web developement'],
                projectIndexs: ['001','002','003'],
                projectImages: ['../../src/assets/images/sample-2.png', '../../src/assets/images/sample-3.png', '../../src/assets/images/sample-4.png']
            }
        },
        methods: {
            afterEnter: function (el) {
                // console.log('----------here');
                this.isActivityCardFinishShow = true;
            },
            selectProject: function(index) {
                // console.log("Select");
                // var projectName = document.getElementsByClassName("project-name");
                // console.log(projectName);
                // console.log(projectName[0]);
                // projectName[0].innerHTML="123";
                this.projectIndex = index;
            },
            handleScroll: function(event) {
                let obj = document.querySelector('.section-developer');
                let {top,bottom} = obj.getBoundingClientRect();
            },
            triggerEvent: function(instance) {
                // console.log(instance);
                // console.log("已加入");

                var trigger = new ScrollTrigger({
                  toggle: {
                    visible: 'visibleClass',
                    hidden: 'hiddenClass'
                  },
                  offset: {
                    x: 0,
                    y: -80
                  },
                  addHeight: true,
                  once: true
                }, document.body, window);


                var callback = function(scrollLeft, scrollTop, width, height){
                    // console.log("Left:"+scrollLeft+ " Top:"+ scrollTop);
                    // console.log(instance.pageIndex);
                    // console.log($(document))

                    if (scrollTop > 100) {
                        instance.isScrollHintShow = false;
                    } else {
                        instance.isScrollHintShow = true;
                    }

                    if (scrollTop > 1800) {
                        instance.isPageIndicatorShow = true;
                    } else {
                        instance.isPageIndicatorShow = false;
                    }

                    if (scrollTop > 1800 && scrollTop < 3800) {
                        instance.pageIndex = 1;
                    } else if (scrollTop > 3800 && scrollTop < 4800) {
                        instance.pageIndex = 2;
                    } else if (scrollTop > 4800 && scrollTop < 6000) {
                        instance.pageIndex = 3;
                    } else if (scrollTop > 6000) {
                        instance.pageIndex = 4;
                    }


                    if (scrollTop > 1000) {
                        instance.isMemberCardShow = true;
                    }
                    if (scrollTop > 1900) {
                        instance.isActivityCardShow = true;
                    }
                    if (scrollTop > 2900) {
                        instance.isFeedbackCardShow = true;
                    }
                };

                trigger.attach(callback);
            },
            setWindowHeight: function() {
                var windowHeight = window.innerHeight;
                var windowWidth = window.innerWidth;
                document.body.style.height = windowHeight + "px";
                console.log(windowWidth);
                var feedbackCard = document.getElementsByClassName("feedback-card");
                if (windowWidth < 920) {
                    this.swiper.params.slidesPerView = 1;
                    this.compact = true;
                } else {
                    this.compact = false;
                }
            },
            setFeedbackTimer: function() {
                var instance = this;
                setInterval(function(){
                    instance.feedbackItems.splice(0, 1);
                    instance.partialIndex = instance.partialIndex==0 ? 1 : 0;
                    setTimeout(function(){
                        instance.feedbackItems.splice(2, 0, instance.currentFeedbackIndex);
                        if (instance.currentFeedbackIndex < 7) {
                            instance.currentFeedbackIndex++;
                        } else {
                            instance.currentFeedbackIndex=1;
                        }
                    }, 500);
                }, 5000);
            },
            shouldShowLeft: function(index) {
                // return true;
                return index%2 == this.partialIndex || this.compact;
            },
            shouldShowRight: function(index) {
                // return false;
                return index%2!=this.partialIndex && !this.compact;
            }
        },
        computed: {
            swiper() {
                return this.$refs.mySwiper.swiper
            }
        },
        created() {
            // window.addEventListener('scroll', this.handleScroll);
            var instance = this;
            document.addEventListener('DOMContentLoaded', this.triggerEvent(this));
            window.addEventListener("resize", this.setWindowHeight);
        },
        destroyed() {
            // 記得要移除掉 Evenet Listener，否則再下一次進來這個 Component 時就會不運作
            var instance = this;
            document.removeEventListener('DOMContentLoaded', this.triggerEvent(instance));
            document.removeEventListener('resize', this.setWindowHeight);
            // window.removeEventListener('scroll', this.handleScroll);
        },
        mounted() { 
            this.setWindowHeight()
            this.setFeedbackTimer()
            // this.$nextTick(() => {
                // this.initParticleJS()   
            // });
            this.$nextTick(() => {
                const particlesJS = window.particlesJS;
                // particlesJS.load('particles', 'dist/particles.json', function() {
                // });
                particlesJS('particles', {
                  "particles": {
                    "number": {
                      "value": 24,
                      "density": {
                        "enable": true,
                        "value_area": 800
                      }
                    },
                    "color": {
                      "value": "random"
                    },
                    "shape": {
                      "type": "circle",
                      "stroke": {
                        "width": 0,
                        "color": "#000000"
                      },
                      "polygon": {
                        "nb_sides": 5
                      },
                      "image": {
                        "src": "img/github.svg",
                        "width": 100,
                        "height": 100
                      }
                    },
                    "opacity": {
                      "value": 0.5,
                      "random": false,
                      "anim": {
                        "enable": false,
                        "speed": 1,
                        "opacity_min": 0.1,
                        "sync": false
                      }
                    },
                    "size": {
                      "value": 5,
                      "random": true,
                      "anim": {
                        "enable": false,
                        "speed": 40,
                        "size_min": 0.1,
                        "sync": false
                      }
                    },
                    "line_linked": {
                      "enable": false,
                      "distance": 150,
                      "color": "#ffffff",
                      "opacity": 0.4,
                      "width": 1
                    },
                    "move": {
                      "enable": true,
                      "speed": 2,
                      "direction": "none",
                      "random": false,
                      "straight": false,
                      "out_mode": "out",
                      "bounce": false,
                      "attract": {
                        "enable": false,
                        "rotateX": 600,
                        "rotateY": 1200
                      }
                    }
                  },
                  "interactivity": {
                    "detect_on": "canvas",
                    "events": {
                      "onhover": {
                        "enable": true,
                        "mode": "repulse"
                      },
                      "onclick": {
                        "enable": true,
                        "mode": "push"
                      },
                      "resize": true
                    },
                    "modes": {
                      "grab": {
                        "distance": 400,
                        "line_linked": {
                          "opacity": 1
                        }
                      },
                      "bubble": {
                        "distance": 400,
                        "size": 40,
                        "duration": 2,
                        "opacity": 8,
                        "speed": 3
                      },
                      "repulse": {
                        "distance": 200,
                        "duration": 0.4
                      },
                      "push": {
                        "particles_nb": 4
                      },
                      "remove": {
                        "particles_nb": 2
                      }
                    }
                  },
                  "retina_detect": true
                })
            });
        },
        components: {
            HeaderBar,
            FooterBar,
            PageIndicator,
            Card,
            MemberCard,
            FeedbackCard
        }
    }
</script>

<style scope lang="sass">
    @import '~styles/main.sass'
    @import '~styles/swiper.css'

    [v-cloak]
        display: none;

    .swiper-container
        height: 480px
        @include pc-width
            height: 600px

    .swiper-button-prev
        width: 15px
        height: 36px
        background-position: center
        background-size: cover
        background-image: url('https://i.imgur.com/ywIpxCL.png')
        @include pc-width
            width: 20px
            height: 48px
            transform: translateX(-56px)

    .swiper-button-next
        width: 15px
        height: 36px
        background-position: center
        background-size: cover
        background-image: url('https://i.imgur.com/ZVReTib.png')
        @include pc-width
            width: 20px
            height: 48px
            transform: translateX(56px)

    #particles
        position: absolute;
        width: 100%
        height: 100%
        // background-color: #b61924;
        background-repeat: no-repeat
        background-size: cover
        background-position: 50% 50%

    path 
        stroke-dasharray: 2000
        stroke-dashoffset: 2000
        animation: dash 1.0s linear forwards

    .container
        margin-left: auto
        margin-right: auto

    .cardAnimation
        transition-duration: 0.4s

    .section-landing
        width: 100%
        height: 480px
        @include pc-width
            height: 640px

        .landing-logo
            margin-left: auto
            margin-right: auto
            display: block
            width: 400px
            height: 200px
            top: 50%
            transform: translateY(-50%)
            @include pc-width
                transform: translateY(-80%)

    .section-about
        background: #f8f8f8
        height: 600px
        h2
            width: 80%
            max-width: 720px
            margin-left: auto
            margin-right: auto

        .about-container
            padding-top: 24px
            padding-bottom: 24px
            .about-item
                margin-top: 32px
                @include pc-width
                    margin-left: 72px
                    margin-right: 72px
                h1
                    font-size: 20px
                    font-weight: 400
                    line-height: 16px
                .landing-logo
                    width: 120px
                    height: 120px
                    display: block
                    margin-left: auto
                    margin-right: auto

                .landing-logo-long
                    width: 150px
                    height: 120px
                    display: block
                    margin-left: auto
                    margin-right: auto

            @include pc-width
                display: flex
                justify-content: center

    .section-member
        background: $default-background-color

        h2
            width: 80%
            max-width: 720px
            margin-left: auto
            margin-right: auto

        .member-container
            width: 100%
            max-width: 1200px
            // display: flex
            // justify-content: flex-start
            margin-top: 32px
            margin-left: auto
            margin-right: auto
            .member-card
                margin-left: auto
                margin-right: auto
                margin-top: 32px
                background: white
                border: solid 1px $default-background-gray-color
                width: 288px
                height: 410px
                &:hover
                    transform: translateY(-16px)
                    box-shadow: 0px 10px 20px RGBA(0,0,0,0.25)

                @include pc-width
                    // margin-top: 40px
                    // margin-left: 36px
                    // margin-right: 36px
                    margin-left: 0
                    margin-right: 0
                    width: 360px
                    height: 510px


            @include pc-width
                display: flex
                justify-content: space-around

        .check-more
            width: 100%
            max-width: 1200px
            font-weight: 300
            margin-left: auto
            margin-right: auto
            margin-top: 0px
            text-align: center
            a
                pointer: cursor
                text-decoration: none
                text-align: center
                color: #01BAD4
                display: inline-block
                margin-left: auto
                margin-right: auto
                &:hover
                    pointer: cursor
                    &:after
                        transform: scale3d(1, 1, 1)
                &:after
                    content: ''
                    position: absolute
                    background: #01BAD4
                    transition: transform 0.3s
                    transition-timing-function: cubic-bezier(1, 0.68, 0.16, 0.9)
                    bottom: -6px
                    left: -6px
                    height: 2px
                    width: calc(100% + 12px)
                    transform: scale3d(0, 1, 1)
                    transform-origin: 50% 50%


    .section-activity
        background: #f8f8f8
        height: 900px
        h2
            width: 80%
            max-width: 720px
            margin-left: auto
            margin-right: auto
        // h1
        //     color: white
        .activity-container
            width: 100%
            max-width: 1200px
            // display: flex
            // justify-content: space-around
            margin-top: 32px
            margin-left: auto
            margin-right: auto
            .activity-card
                box-shadow: 0px 5px 15px RGBA(0,0,0,0.15)
                margin-left: auto
                margin-right: auto
                margin-top: 32px
                background: white
                width: 288px
                height: 400px

                @include pc-width
                    margin-left: 0
                    margin-right: 32px
                    width: 360px
                    height: 500px

                &:hover
                    transform: translateY(-16px)
                    box-shadow: 0px 10px 20px RGBA(0,0,0,0.25)

            @include pc-width
                display: flex
                justify-content: space-around

        .check-more
            width: 100%
            max-width: 1200px
            font-weight: 300
            margin-left: auto
            margin-right: auto
            margin-top: 0px
            text-align: center
            pointer: cursor
            a
                pointer: cursor
                text-decoration: none
                text-align: center
                color: #01BAD4
                display: inline-block
                margin-left: auto
                margin-right: auto
                &:hover
                    &:after
                        transform: scale3d(1, 1, 1)
                &:after
                    content: ''
                    position: absolute
                    background: #01BAD4
                    transition: transform 0.2s
                    transition-timing-function: cubic-bezier(1, 0.68, 0.16, 0.9)
                    bottom: -6px
                    left: -6px
                    height: 3px
                    width: calc(100% + 12px)
                    transform: scale3d(0, 1, 1)
                    transform-origin: 50% 50%

                
    .section-feedback
        height: auto
        .feedback-container
            margin-left: auto
            margin-right: auto
            height: 1500px
            @include pc-width
                width: 1200px
                height: 800px
            .feedback-card-container
                transition: all 1.5s

            .feedback-card
                width: 100%
                max-width: 1200px
                margin-left: auto
                margin-right: auto
                transition: all 1s

        .contact-container
            max-width: 560px
            width: 80%
            margin-left: auto
            margin-right: auto
            margin-top: 0px
            margin-bottom: 32px
            &:hover 
                .icon-hand
                    transform: rotate(20deg)
            .icon-hand
                width: 64px
                height: 64px
                transform: translateY(16px)
                display: block
                background-size: cover
                background-position: center
                background-image: url('~assets/images/icon-hand.png')
                transition-duration: 0.2s
                transform-origin: 0% 100%
                margin-left: auto
                margin-right: auto
                margin-bottom: 24px
                @include pc-width
                    display: inline-block
                    margin-bottom: 0px
            .join-text
                display: block
                color: $text-color-normal
                font-size: 30px
                font-weight: 700
                margin-left: 24px
                text-align: center
                @include pc-width
                    font-size: 36px
                    display: inline-block
                    text-align: left
            .contact-email
                margin-top: 16px
                text-align: center
                @include pc-width
                    margin-top: 24px
                a
                    color: $text-color-gray-light
                    font-size: 16px
                    text-align: center
                    @include pc-width
                        text-align: left
                        font-size: 20px
                        text-align: center


    
    .hiddenClass 
        transition: all 0.8s ease
        opacity: 0.0
        transform: translateY(120px)
    
    .visibleClass 
        transition: all 0.8s ease
        opacity: 1.0
        transform: translateY(0px)


    .fade-text-enter-active, .fade-text-leave-active 
        transition: opacity 0.3s ease

    .fade-text-enter, .fade-text-leave-active
        opacity: 0


    .fade-delay-bg-enter
        opacity: 0.04
        transform: translateY(200px)
    .fade-delay-bg-enter-active
        transition: all 0.8s cubic-bezier(0.22, 0.86, 0.72, 0.99)
    .fade-delay-bg-enter-to
        opacity: 0.04
        transform: translateY(0px)

    .fade-delay1-enter
        opacity: 0
        transform: translateY(200px)
    .fade-delay1-enter-active
        transition: all 1.2s cubic-bezier(0.22, 0.86, 0.72, 0.99)
    .fade-delay1-enter-to
        opacity: 1
        transform: translateY(0px)

    .fade-delay2-enter
        opacity: 0
        transform: translateY(200px)
    .fade-delay2-enter-active
        transition: all 1.2s cubic-bezier(0.22, 0.86, 0.72, 0.99) 0.15s
    .fade-delay2-enter-to
        opacity: 1
        transform: translateY(0px)

    .fade-delay3-enter
        opacity: 0
        transform: translateY(200px)
    .fade-delay3-enter-active
        transition: all 1.2s cubic-bezier(0.22, 0.86, 0.72, 0.99) 0.3s
    .fade-delay3-enter-to
        opacity: 1
        transform: translateY(0px)

    .fade-delay4-enter
        opacity: 0
        transform: translateY(200px)
    .fade-delay4-enter-active
        transition: all 0.8s cubic-bezier(0.22, 0.86, 0.72, 0.99) 0.45s
    .fade-delay4-enter-to
        opacity: 1
        transform: translateY(0px)


    .fade-delay5-enter
        opacity: 0
        transform: translateY(200px)
    .fade-delay5-enter-active
        transition: all 0.8s cubic-bezier(0.22, 0.86, 0.72, 0.99) 0.6s
    .fade-delay5-enter-to
        opacity: 1
        transform: translateY(0px)


    .fade-enter-active-image
        transform-origin: 100% 50%;
        // animation: imageIn 0.5s cubic-bezier(1,0.01,0.38,1) 1.2s forwards
        animation: imageIn 0.8s cubic-bezier(0.23,1.02,0.34,0.9) 1.1s forwards
    .fade-enter-content
        opacity: 0
        transition: all 0.0s
    .fade-enter-active-headerbar
        animation: headerBarIn 0.6s ease-out 0.0s forwards
    .fade-enter-active-scroll
        animation: scrollIconInPhone 0.6s ease-out 0.0s forwards
        @include pc-width
            animation: scrollIconIn 0.6s ease-out 0.0s forwards


    .fade-enter-active-div-1
        animation: divSlideIn 0.4s cubic-bezier(1,0.01,0.38,1) 0.5s forwards
    .fade-enter-active-content-1
        animation: contentIn 0.4s ease-out 0.3s forwards
    .fade-enter-active-content-2
        animation: contentIn 0.4s ease-out 0.5s forwards
    .fade-enter-active-content-3
        animation: contentIn 0.4s ease-out 0.7s forwards
    .fade-enter-active-content-4
        animation: contentIn 0.5s ease-out 0.9s forwards
    .fade-enter-active-content-5
        animation: contentIn 0.5s ease-out 1.1s forwards
    .fade-enter-active-content
        animation: contentIn 0.8s ease-out 0.5s forwards


    .feedback-update-enter
        opacity: 0
        transform: translateY(120px)

    .feedback-update-leave-to
        opacity: 0
        
    .feedback-update-leave-active
        width: 100%
        position: absolute
        transform: translateY(-120px)

    @keyframes dash 
        from 
            stroke-dashoffset: 2000
  
        to
            stroke-dashoffset: 0

    @keyframes imageIn 
        0%
            transform: scale3d(1,1,1)
            transform-origin: 100% 50%
        100%
            transform: scale3d(0,1,1)
            transform-origin: 100% 50%

    @keyframes headerBarIn
        0%
            transform: translateY(-140px)
            opacity: 1.0
        100%
            transform: translateY(0px)
            opacity: 1.0

    @keyframes scrollIconInPhone
        0%
            transform: translateY(0px)
            opacity: 0.0
        100%
            opacity: 1.0
            transform: translateY(-50%)

    @keyframes scrollIconIn
        0%
            transform: translateY(0px)
            opacity: 0.0
        100%
            opacity: 1.0
            // transform: translateY(-50%)
            // @include pc-width
            transform: translateY(-80%)

    @keyframes divSlideIn 
        0%
            transform: scale3d(0,1,1)
            transform-origin: 0% 50%
            opacity: 1.0
        100%
            transform: scale3d(1,1,1)
            transform-origin: 0% 50%
            opacity: 1.0

    @keyframes imageFadeIn 
        0%
            opacity: 0
        100%
            opacity: 1.0

    @keyframes selectFadeIn 
        0%
            opacity: 0
            // transform: translateY(10px)
            transform: scale3d(0,1,1)
            transform-origin: 0% 50%
        100%
            opacity: 1.0
            // transform: translateY(0px)
            transform: scale3d(1,1,1)
            transform-origin: 0% 50%

    @keyframes contentIn 
        0%
            transform: translateY(60px)
            opacity: 0
        100%
            transform: translateY(0px)
            opacity: 1.0

</style>