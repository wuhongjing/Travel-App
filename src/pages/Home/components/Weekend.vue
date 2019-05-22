<template>
  <section class="weekend">
     <div class="recoTitle">周末去哪儿</div>
     <ul>
        <li class="item border-bottom" v-for="item in weekendList" :key="item.id">
           <div class="itemPic"><img :src="item.imgUrl" /></div>
           <div class="itemInfo">
              <p class="itemTit">{{item.title}}</p>
              <p class="itemDesc">{{item.desc}}</p>
           </div>
        </li>
     </ul>
  </section>
</template>

<script>
export default {
  name: 'Weekend',
  props: {
    weekendList: Array
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
   width: 100%
   .itemPic
      overflow: hidden
      height: 0
      padding-bottom:33.9%
      > img
        width: 100%
   .itemInfo
      padding: .1rem
      min-width: 0
      .itemTit
         line-height: .5rem
         font-size: .32rem
         ellipsis()
      .itemDesc
         line-height: .4rem
         font-size: .28rem
         color: #ccc
         ellipsis()
</style>
