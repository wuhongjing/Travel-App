<template>
  <section class="Nav">
    <swiper>
      <swiper-slide v-for="(page,index) in pages" :key="index">
        <ul class="navWrap" v-for="(item,index) in page" :key="index">
          <li><img :src="item.imgUrl" /><p>{{item.desc}}</p></li>
        </ul>
      </swiper-slide>
    </swiper>
  </section>
</template>

<script>
export default {
  name: 'Nav',
  data () {
    return {
      swiperOption: {
        loop: false
      },
      iconList: [{
        'id': '0001',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
        'desc': '景点门票'
      }, {
        'id': '0002',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1711/df/86cbcfc533330d02.png',
        'desc': '滑雪季'
      }, {
        'id': '0003',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1710/a6/83f636bd75ae6302.png',
        'desc': '泡温泉'
      }, {
        'id': '0004',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
        'desc': '景点门票'
      }, {
        'id': '0005',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1711/df/86cbcfc533330d02.png',
        'desc': '滑雪季'
      }, {
        'id': '0006',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1710/a6/83f636bd75ae6302.png',
        'desc': '泡温泉'
      }, {
        'id': '0007',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1611/54/ace00878a52d9702.png',
        'desc': '景点门票'
      }, {
        'id': '0008',
        'imgUrl': 'http://img1.qunarzz.com/piao/fusion/1711/df/86cbcfc533330d02.png',
        'desc': '滑雪季'
      }]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const num = Math.floor(index / 8)
        if (!pages[num]) {
          pages[num] = []
        }
        pages[num].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~style/varibles.styl'
@import '~style/mixins.styl'
.Nav
  overflow: hidden
  height: 0
  padding-bottom: 50%
  .navWrap
    > li
      overflow: hidden
      float: left
      height: 0
      width: 25%
      padding-bottom: 25%
      > img
        display: block
        width: 60%
        margin: 0.15rem auto 0.10rem auto
      > p
        height: .44rem
        line-height: .44rem
        text-align: center
        color: $darkText
        ellipsis()
</style>
