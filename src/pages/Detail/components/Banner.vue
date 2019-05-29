<template>
  <section>
    <div class="banner" @click="handleBannerClick">
      <img class="picShow" :src="bannerImg" />
      <div class="bannerInfo">
        <p class="bannerTit">{{this.sightName}}</p>
        <p class="bannerNum">
          <i class="iconfont picIcon">&#59026;</i>{{this.gallaryImgs.length}}
        </p>
      </div>
    </div>
    <Gallary :gallaryImgs="gallaryImgs" v-show="gallaryShow" @close="handleGallaryClose"></Gallary>
  </section>
</template>

<script>
import Gallary from 'common/Gallary/Gallary'

export default {
  name: 'Banner',
  components: {
    Gallary
  },
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data () {
    return {
      gallaryShow: false
    }
  },
  methods: {
    handleBannerClick () {
      this.gallaryShow = true
    },
    handleGallaryClose () {
      this.gallaryShow = false
    }
  }
}
</script>

<style lang="stylus" scoped>
.banner
  position: relative
  overflow: hidden
  height: 0
  padding-bottom: 55%
  .picShow
    width:100%
  .bannerInfo
    display: flex
    position: absolute
    left: 0
    right: 0
    bottom: 0
    line-height: .6rem
    .bannerTit
      flex: 1
      color:#fff
      font-size: .3rem
      padding: 0 0.2rem
    .bannerNum
      color: #fff
      padding: 0 .4rem
      margin: .1rem .2rem 0 0
      height: .4rem
      line-height: .4rem
      border-radius: 1rem
      background: rgba(0, 0, 0, 0.7)
      font-size: .24rem
      .picIcon
        font-size: .26rem
        margin-right:.1rem
</style>
