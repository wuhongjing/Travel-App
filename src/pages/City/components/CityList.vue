<template>
  <section class="cityList" ref="wrapper">
     <div>
        <div class="area">
          <h3 class="title border-topbottom">当前位置</h3>
          <ul class="citySearch">
              <li><p>{{this.$store.state.city}}</p></li>
          </ul>
        </div>
        <div class="area">
          <h3 class="title border-topbottom">热门城市</h3>
            <ul class="citySearch">
              <li v-for="item in hotCities" :key="item.id" @click="handleChangeCity(item.name)"><p>{{item.name}}</p></li>
          </ul>
        </div>
        <div class="area" v-for="(item,key) in cities" :key="key" :ref="key">
          <h3 class="title border-topbottom">{{key}}</h3>
          <ol class="areaList">
            <li
               class="list border-bottom"
               v-for="innerItem in item"
               :key="innerItem.id"
               @click="handleChangeCity(innerItem.name)"
               >
               {{innerItem.name}}
            </li>
          </ol>
        </div>
     </div>
  </section>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    cities: Object,
    hotCities: Array,
    letter: String
  },
  methods: {
    handleChangeCity (city) {
      this.$store.commit('cityChange', city)
      this.$router.push('/')
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      // console.log(this.letter)
      if (this.letter) {
        let element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~style/varibles.styl'
.border-topbottom
  &:before
    border-color: #ccc
  &:after
    border-color: #ccc
.border-bottom
  &:before
    border-color: #ccc
.cityList
  overflow: hidden
  position: absolute
  top: 1.58rem
  left: 0
  right: 0
  bottom: 0
  .title
    line-height: .5rem
    background: #eee
    padding-left: .2rem
    color: #666
    font-size: .26rem
  .citySearch
    padding: .1rem .6rem .1rem .1rem
    overflow: hidden
    >li
      float: left
      width:33.33%
      >p
        padding: .1rem 0
        margin: .1rem
        text-align: center
        border-radius: .06rem
        border: .02rem solid #ccc
  .areaList
    line-height: .76rem
    padding: 0 .2rem
</style>
