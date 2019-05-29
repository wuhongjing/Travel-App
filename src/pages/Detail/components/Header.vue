<template>
  <div class="header">
    <router-link class="headerBack" tag="div" to='/' v-show="isShow">
      <i class="iconfont backIcon">&#58916;</i>
    </router-link>
    <div class="headerFixed" v-show="! isShow" :style="opacityStyle">
      <router-link to='/' tag="div" class="cityBack">
        <i class="iconfont back-icon">&#58916;</i>
      </router-link>
      景点详情
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header',
  data () {
    return {
      isShow: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      // 考虑到兼容性问题
      let scrollTop = document.documentElement.scrollTop || document.body.scrollTop
      if (scrollTop > 60) {
        let opacity = scrollTop / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.isShow = false
      } else {
        this.isShow = true
      }
    }
  },
  mounted () {
    window.addEventListener('scroll', this.handleScroll)
  },
  unmounted () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
@import '~style/varibles.styl'

.header
  z-index: 2
  position: absolute
  top: 0.2rem
  left: 0.2rem
  width: .65rem
  height: .65rem
  border-radius: .4rem
  background: rgba(0, 0, 0, .8)
  text-align:center
  .backIcon
    font-size: .32rem
    color: #fff
    line-height: .65rem
  .headerFixed
    position: fixed
    top: 0
    left: 0
    width:100%
    height: $headerHight
    line-height: $headerHight
    color: #fff
    font-size: .32rem
    text-align: center
    background: $bgcolor
    .cityBack
      position: absolute
      top: 0
      left: .15rem
      font-size: .32rem

</style>
