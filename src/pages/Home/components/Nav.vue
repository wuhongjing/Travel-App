<template>
  <section class="Nav">
    <swiper  :options="swiperOption">
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
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOption: {
        loop: false
      }
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
  margin-top: .1rem
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
