<template>
  <section class="recommend">
     <div class="recoTitle">热销推荐</div>
     <ul>
        <li class="item border-bottom">
           <div class="itemPic"><img src="http://img1.qunarzz.com/sight/p0/1708/2b/2b3b94de99c0a425a3.img.jpg_200x200_2458ffb2.jpg" /></div>
           <div class="itemInfo">
              <p class="itemTit">北京世界园艺博览会北京世界园艺</p>
              <p class="itemDesc">北京世界园艺博览会北京世界园艺博览会</p>
              <button class="itemBtn">查看详情</button>
           </div>
        </li>
        <li class="item border-bottom">
           <div class="itemPic"><img src="http://img1.qunarzz.com/sight/p0/1708/2b/2b3b94de99c0a425a3.img.jpg_200x200_2458ffb2.jpg" /></div>
           <div class="itemInfo">
              <p class="itemTit">北京世界园艺博览会北京世界园艺</p>
              <p class="itemDesc">北京世界园艺博览会北京世界园艺博览会</p>
              <button class="itemBtn">查看详情</button>
           </div>
        </li>
        <li class="item border-bottom">
           <div class="itemPic"><img src="http://img1.qunarzz.com/sight/p0/1708/2b/2b3b94de99c0a425a3.img.jpg_200x200_2458ffb2.jpg" /></div>
           <div class="itemInfo">
              <p class="itemTit">北京世界园艺博览会北京世界园艺</p>
              <p class="itemDesc">北京世界园艺博览会北京世界园艺博览会</p>
              <button class="itemBtn">查看详情</button>
           </div>
        </li>
     </ul>
  </section>
</template>

<script>
export default {
  name: 'Recommend'
}
</script>

<style lang="stylus" scoped>
@import '~style/varibles.styl'
@import '~style/mixins.styl'

.recoTitle
   margin-top: .2rem
   line-height: .8rem
   background: #eee
   text-indent: .2rem
.item
   display: flex
   height: 1.9rem
   .itemPic
      width: 1.7rem
      height: 1.7rem
      padding: .15rem
      > img
        width:100%
   .itemInfo
      flex: 1
      padding: .1rem
      .itemTit
         line-height: .54rem
         font-size: .32rem
         ellipsis()
      .itemDesc
         line-height: .4rem
         font-size: .3rem
         color: #ccc
         ellipsis()
      .itemBtn
         line-height: .44rem
         background: #ff9300
         border-radius: 0.06rem
         padding: 0 0.1rem
         margin-top: .14rem
         color: #fff
         font-size: .25rem
</style>
