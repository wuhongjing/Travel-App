<template>
  <section class="indexSwiper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for="item in swiperList" :key="item.id"><img class="picShow" :src="item.imgUrl"></swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </section>
</template>

<script>
export default {
  name: 'indexSwiper',
  props: {
    swiperList: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: 5000
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
.indexSwiper >>> .swiper-pagination-bullet-active
   background: #fff
.indexSwiper
   overflow: hidden
   width:100%
   height:0
   padding-bottom:31.3%
   background:#eee
   .picShow
      width:100%
</style>
