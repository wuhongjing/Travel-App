<template>
  <section class="banner">
    <img class="picShow" src="http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg" />
    <div class="bannerInfo">
      <p class="bannerTit">北京市东城区景山前街4号</p>
      <p class="bannerNum">
        <i class="iconfont picIcon">&#59026;</i>39
      </p>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Banner'
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
