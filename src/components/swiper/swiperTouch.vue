<template>
    <div class="swiper-box">
        <div class="swiper-left">
            <img src="../../../static/images/touch-title.png" alt="" class="swiper-left-pic">
        </div>
        <div class="swiper-right">
            <scroll-view class="swiper"  scroll-x="true">
                <div class="swiper-item" v-for="(item,index) in swiperContent" :key="index">
                    <div class="swiper-content">
                        <div class="swiper-content-img">
                            <img :src="item.img" alt="" class="content-img-pic">
                        </div>
                        <div class="swiper-content-text">
                            <span class="content-text-title">{{item.title}}&nbsp;&nbsp;</span>
                            <span>{{item.desc}}</span>
                        </div>
                    </div>
                </div>
                <div class="swiper-more" v-if="loadingMore">
                    <div class="more-text" @click="showMore()">
                        <span>查看更多&nbsp;></span>
                    </div>
                </div>
            </scroll-view>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        swiperContent: Array,
        loadingMore : {
            type: Boolean,
            default: true
        }
    },
    methods: {
        showMore () {
            this.$emit('showMore')
            // console.log(this.swiperContent,22222222)
            
        }
    }
}
</script>

<style lang="stylus" scoped>
@import  '../../common/style/mixin'
    .swiper-box
        // wh(100%, 200rpx)
        width 750rpx
        height 200rpx
        margin-top 10rpx
        flex(space-between)
        .swiper-left
            wh(82rpx, 150rpx)
            .swiper-left-pic
                width 100%
                height 100%
       
        .swiper-right
            margin-left 10rpx
            wh(670rpx, 150rpx)
            .swiper
                wh(670rpx, 150rpx)
                white-space nowrap
                .swiper-item
                    wh(400rpx, 180rpx)
                    display inline-block
                    background-color #f8f8f8
                    .swiper-content
                        flex(space-between)
                        margin-left 20rpx
                        height 150rpx
                        margin-right 20rpx
                        .swiper-content-img
                            wh(100rpx, 100rpx)
                            margin-right 10rpx
                            .content-img-pic
                                wh(100%, 100%)
                        .swiper-content-text
                            width 324rpx
                            margin-right 15rpx
                            margin-left 10rpx
                            font-size 23rpx
                            display: -webkit-box;
                            overflow: hidden;
                            text-overflow: ellipsis;
                            word-wrap: break-word;
                            white-space: normal !important;
                            -webkit-line-clamp: 2;
                            -webkit-box-orient: vertical;
                            .content-text-title
                                font-weight bold
                                font-size 30rpx
                .swiper-more
                    display inline-block
                    color #282828
                    wh(200rpx, 60rpx)
                    font-size 20rpx
                    hlh(60rpx)
                    position:relative
                    bottom 40rpx

                    .more-text
                        margin-left 40rpx
                        
</style>
