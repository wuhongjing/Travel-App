<template>
  <div class="gallary" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper :options="swiperOption">
        <!-- slides -->
        <swiper-slide v-for="(item,index) in gallaryImgs" :key="index">
          <img class="imgShow" :src="item" />
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Gallary',
  props: {
    gallaryImgs: {
      type: Array
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observer: true,
        observeParents: true
      }
    }
  },
  methods: {
    handleGallaryClick () {
      this.$emit('close')
    }
  }
}
</script>

<style lang="stylus" scoped>
.gallary >>> .swiper-container
  overflow: inherit
.gallary
  display: flex
  flex-direction: column
  justify-content: center
  position: fixed
  z-index: 99
  top: 0
  left: 0
  right: 0
  bottom: 0
  background: #000
  .wrapper
    height: 0
    width: 100%
    padding-bottom: 100%
    .imgShow
      width:100%
  .swiper-pagination
    color:#fff
    bottom: -1rem
</style>
