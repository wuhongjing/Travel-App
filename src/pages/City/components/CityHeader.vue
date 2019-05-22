<template>
  <section class="cityHeader">
    <router-link to='/' tag="div" class="cityBack">
      <i class="iconfont back-icon">&#58916;</i>
    </router-link>
     国内城市
  </section>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
@import '~style/varibles.styl'

.cityHeader
  position: relative
  overflow: hidden
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
    .back-icon
      font-size: 0.36rem
</style>
