<template>
  <section class="indexSwiper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide><img class="picShow" src="http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20194/e5104d77fbfdb522bd4fe4f0451e517f.jpg_750x200_7d44f64b.jpg" /></swiper-slide>
      <swiper-slide><img class="picShow" src="http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20195/5eb82a8ca5b0cebb2c3ae1a53a4d8f81.jpg_750x200_645bfba1.jpg"></swiper-slide>
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
   padding-bottom:31.25%
   .picShow
      width:100%
</style>
