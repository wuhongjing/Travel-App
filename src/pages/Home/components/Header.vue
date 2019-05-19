<template>
  <section class="header">
    <div class="headerLeft">
      <i class="iconfont back-icon">&#58916;</i>
    </div>
    <div class="headerSearch">
      <i class="iconfont">&#58930;</i>
      输入城市/景点/游玩主题
    </div>
    <div class="headerRight">
      城市
      <i class="iconfont city-icon">&#58954;</i>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="stylus" scoped>
@import '~style/varibles.styl'

.header
   display:flex
   line-height: 0.86rem
   background: $bgcolor
   color:#fff
   .headerLeft
      width: 0.64rem
      float: left
      text-align: center
      .back-icon
         font-size: 0.36rem
   .headerSearch
      flex:1
      height:0.64rem
      line-height: .64rem
      margin: .12rem 0
      padding-left: 0.2rem
      color: #ccc
      background:#fff
      border-radius: .1rem
   .headerRight
      width: 1.24rem
      float: right
      text-align:center
      .city-icon
         margin-left: -.04rem
         font-size: .25rem
</style>
