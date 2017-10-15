<template lang="html">
    <div>
        <div class="container">
            <transition appear appear-to-class="fade-enter-content"
                                    appear-active-class="fade-enter-active-headerbar">
                <headerBar :showAbout="true" :showWork="false"></headerBar>
            </transition>
            <transition name="slide-fade">
                <pageIndicator v-show="isPageIndicatorShow" class="page-control" :currentIndex="pageIndex"></pageIndicator>
            </transition>
            <section class="section-landing">
                
            </section>
            <section class="section-about">
                
            </section>
            <section class="section-member">
                
            </section>
            <section class="section-activity">
                
            </section>
            <section class="section-feedback">
                
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
    import BackgroundRope from './Element/background.vue';
    import HoverPicture from './Element/hoverPicture.vue';
    import TitleContainer from './Element/title.vue';
    import WorksContainer from './Element/works.vue';
    import ArticleContainer from './Element/article.vue';
    import MoreButton from './Element/moreButton.vue';
    import ScrollTrigger from 'scrolltrigger-classes';
    import ScrollTo from 'vue-scrollto';
    import Rellax from 'rellax';
    import tilt from 'tilt.js';


    var VueScrollTo = require('vue-scrollto');
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

    export default {
        data () {
            return {
                isScrollHintShow: true,
                isDesignContentShow: false,
                isDeveloperContentShow: false,
                isEducatorContentShow: false,
                isWriterContentShow: false,
                isPageIndicatorShow: false,
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
            selectProject: function(index) {
                console.log("Select");
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
                console.log(instance);
                console.log("已加入");

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

                console.log("已加入" + trigger);

                var callback = function(scrollLeft, scrollTop, width, height){
                    console.log("Left:"+scrollLeft+ " Top:"+ scrollTop);
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


                    if (scrollTop > 1400) {
                        instance.isDesignContentShow = true;
                        // if (scrollTop < 4300) {
                            // instance.pageIndex = 2;
                            // $(document).trigger('index.update', [2]);
                        // }
                    }
                    if (scrollTop > 3400) {
                        instance.isDeveloperContentShow = true;
                    }
                    if (scrollTop > 4300) {
                        instance.isEducatorContentShow = true;
                        // if (scrollTop < 5300) {
                            // instance.pageIndex = 3;
                            // $(document).trigger('index.update', [3]);
                        // }
                    }
                    if (scrollTop > 5500) {
                        instance.isWriterContentShow = true;
                        // instance.pageIndex = 4;
                        // $(document).trigger('index.update', [4]);
                    }
                };

                trigger.attach(callback);
            },
            setWindowHeight: function() {
                var windowHeight = window.innerHeight;
                document.body.style.height = windowHeight + "px";
                console.log(document.body.style.height);
                var aboutSection = document.getElementsByClassName("section-about");
                console.log(aboutSection);
                if (windowHeight > 1200) {
                    aboutSection[0].style.height = windowHeight-320 + 'px';
                    aboutSection[0].style.marginTop = (windowHeight-1200)*0.5+64 + 'px';
                } else {
                    aboutSection[0].style.height = 720 + 'px';
                    // aboutSection[0].style.marginTop = 64 + 'px';

                }
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
            document.removeEventListener('DOMContentLoaded', this.triggerEvent(instance))
            // window.removeEventListener('scroll', this.handleScroll);
        },
        mounted() { 
            console.log(this.isDesignContentShow);
            this.isDesignContentShow = false;
            this.isEducatorContentShow = false;
            this.isWriterContentShow = false;
            this.setWindowHeight()
            $('.header-picture-container').tilt({
                // glare: true,
                scale: 1.05,
                perspective: 1500,
                transition: true,
                speed: 2000
            });
            $('.work-1-container').tilt({
                scale: 1.1,
                maxGlare: .5,
                perspective: 1500,
                transition: true
            });
            $('.work-2-container').tilt({
                scale: 1.1,
                perspective: 1500,
                transition: true
            });
            $('.work-3-container').tilt({
                scale: 1.1,
                perspective: 1500,
                transition: true
            });
            $('.work-4-container').tilt({
                scale: 1.1,
                perspective: 1500,
                transition: true
            });
            $('.developer-container').tilt({
                scale: 1.02,
                perspective: 3000,
                transition: true
            });
            $('.educator-work-1').tilt({
                scale: 1.05,
                perspective: 900,
                transition: true
            });
            $('.educator-work-2').tilt({
                scale: 1.05,
                perspective: 900,
                transition: true
            });
            $('.educator-work-3').tilt({
                scale: 1.05,
                perspective: 900,
                transition: true
            });
            var rellax = new Rellax('.rellax', {
                speed: 4,
                center: false,
                round: true,
            });
        },
        components: {
            HeaderBar,
            FooterBar,
            TitleContainer,
            WorksContainer,
            ArticleContainer,
            BackgroundRope,
            HoverPicture,
            MoreButton,
            PageIndicator
        }
    }
</script>

<style scope lang="sass">
    @import '~styles/main.sass'

    [v-cloak]
        display: none;
    
    .container
        max-width: 2200px
        margin-left: auto
        margin-right: auto

    
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
        transition: all 0.8s cubic-bezier(0.22, 0.86, 0.72, 0.99)
    .fade-delay1-enter-to
        opacity: 1
        transform: translateY(0px)

    .fade-delay2-enter
        opacity: 0
        transform: translateY(200px)
    .fade-delay2-enter-active
        transition: all 0.8s cubic-bezier(0.22, 0.86, 0.72, 0.99) 0.15s
    .fade-delay2-enter-to
        opacity: 1
        transform: translateY(0px)

    .fade-delay3-enter
        opacity: 0
        transform: translateY(200px)
    .fade-delay3-enter-active
        transition: all 0.8s cubic-bezier(0.22, 0.86, 0.72, 0.99) 0.3s
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
        animation: headerBarIn 1.0s cubic-bezier(1,0.01,0.38,1) 0.6s forwards
    .fade-enter-active-scroll
        animation: scrollIconIn 1.0s cubic-bezier(1,0.01,0.38,1) 0.6s forwards
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

    @keyframes scrollIconIn
        0%
            transform: translateY(120px)
            opacity: 0.0
        100%
            transform: translateY(0px)
            opacity: 1.0

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