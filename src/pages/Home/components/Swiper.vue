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
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        autoplay: 5000
      },
      swiperList: [
        {'id': '0001',
          'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1801/1a/94428c6dea109402.jpg_640x200_2cf590d8.jpg'
        },
        {'id': '0002',
          'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1802/42/7c92b9a381e46402.jpg_640x200_1cdce2a4.jpg'
        }
      ]
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
