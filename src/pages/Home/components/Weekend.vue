<template>
  <section class="weekend">
     <div class="recoTitle">周末去哪儿</div>
     <ul>
        <li class="item border-bottom" v-for="item in recommendList" :key="item.id">
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
  data () {
    return {
      recommendList: [
        {
          'id': '0001',
          'imgUrl': 'http://img1.qunarzz.com/sight/source/1510/6e/1ea71e2f04e.jpg_r_640x214_aa6f091d.jpg',
          'title': '故宫',
          'desc': '细数北京温泉，温暖你的冬天'
        }, {
          'id': '0002',
          'imgUrl': 'http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg',
          'title': '北京必游TOP10',
          'desc': '来北京必去的景点非这些地方莫属'
        }, {
          'id': '0003',
          'imgUrl': 'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg',
          'title': '寻找北京的皇城范儿',
          'desc': '数百年的宫廷庙宇，至今依旧威严霸气'
        }
      ]
    }
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
