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
  data () {
    return {
      recommendList: [
        {
          'id': '0001',
          'imgUrl': 'http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg',
          'title': '故宫',
          'desc': '东方宫殿建筑代表，世界宫殿建筑典范'
        }, {
          'id': '0002',
          'imgUrl': 'http://img1.qunarzz.com/sight/p0/1511/d2/d2aec2dfc5aa771290.water.jpg_140x140_abb362a7.jpg',
          'title': '南山滑雪场',
          'desc': '北京专业级滑雪圣地'
        }, {
          'id': '0003',
          'imgUrl': 'http://img1.qunarzz.com/sight/p0/1501/f4/f467729126949c3a.water.jpg_140x140_ef235b1c.jpg',
          'title': '天安门广场',
          'desc': '我爱北京天安门，天安门上太阳升'
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
