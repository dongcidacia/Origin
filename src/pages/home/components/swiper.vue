<template>
    <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
    <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl"/>
    </swiper-slide>
    <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
    </div>
</template>

<script>
export default {
    name: 'HomeSwiper',
    props: {
        list:Array
    },
    data: function() {
        return {
            swiperOption:{
                pagination: '.swiper-pagination',
                loop:true
            }
        }
    },
    computed: {
        showSwiper () {
            return this.list.length
        }
    }
}
</script>

<style lang="stylus" scoped>
   .wrapper >>> .swiper-pagination-bullet-active
      background: white !important/* 样式穿透 >>> 在wrapper下只要出现对应class就定义样式 */
   .wrapper
      background: gray  
      width: 100%
      overflow: hidden 
      height:0 /* height inherit father height */
      padding-bottom: 29.8%  /* 提前撑起swiper防止载入图片时图片下面的内容在进入网页时抖动 */
    .swiper-img
        width: 100% 
</style>