<template>
  <section class="citySearch">
      <input type="text" class="searchInput" placeholder="输入城市名或拼音" v-model="keyword"/>
      <div class="searchCon" ref="search" v-show="keyword">
        <ul>
          <li class="searchItem border-bottom" v-for="(item,index) in list" :key="index" @click="handleChangeCity(item.name)">{{item.name}}</li>
          <li class="searchItem" v-show="hasNoData">没有找到匹配的数据</li>
        </ul>
     </div>
  </section>
</template>

<script>
import BScroll from 'better-scroll'

export default {
  name: 'citySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  methods: {
    handleChangeCity (city) {
      this.$store.commit('cityChange', city)
      this.$router.push('/')
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearInterval(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setInterval(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.search)
  }
}
</script>

<style lang="stylus" scoped>
@import '~style/varibles.styl'

.citySearch
  height: .72rem
  background: $bgcolor
  padding: 0 .15rem
  .searchInput
    width: 100%
    height:.62rem
    line-height: .62rem
    padding:0 0.1rem
    box-sizing: border-box
    text-align: center
    border-radius: 0.06rem
    color: #666
.searchCon
  overflow: hidden
  position: absolute
  top: 1.58rem
  left: 0
  bottom: 0
  right: 0
  background: #eee
  z-index: 1
  .searchItem
    line-height: .62rem
    padding-left: .2rem
    color: #666
    background: #fff
</style>
