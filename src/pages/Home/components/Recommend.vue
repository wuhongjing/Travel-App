<template>
  <section class="recommend">
     <div class="recoTitle">热销推荐</div>
     <ul>
        <li class="item border-bottom" v-for="item in recommendList" :key="item.id">
           <div class="itemPic"><img :src="item.imgUrl" /></div>
           <div class="itemInfo">
              <p class="itemTit">{{item.title}}</p>
              <p class="itemDesc">{{item.desc}}</p>
              <button class="itemBtn">查看详情</button>
           </div>
        </li>
     </ul>
  </section>
</template>

<script>
export default {
  name: 'Recommend',
  props: {
    recommendList: Array
  }
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
        width: 1.7rem
   .itemInfo
      flex: 1
      padding: .1rem
      min-width: 0
      .itemTit
         line-height: .54rem
         font-size: .32rem
         ellipsis()
      .itemDesc
         line-height: .4rem
         font-size: .28rem
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
