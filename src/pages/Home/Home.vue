<template>
  <section class="home">
    <div>
      <Header></Header>
      <indexSwiper :swiperList="swiperList"></indexSwiper>
      <Nav :iconList="iconList"></Nav>
      <Recommend :recommendList="recommendList"></Recommend>
      <Weekend :weekendList="weekendList"></Weekend>
    </div>
  </section>
</template>

<script>
import Header from './components/Header'
import indexSwiper from './components/Swiper'
import Nav from './components/Nav'
import Recommend from './components/Recommend'
import Weekend from './components/Weekend'
import Axios from 'axios'
import { mapState } from 'vuex'

export default {
  name: 'Home',
  components: {
    Header,
    indexSwiper,
    Nav,
    Recommend,
    Weekend
  },
  data () {
    return {
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: [],
      lastCity: ''
    }
  },
  mounted () {
    this.lastCity = this.city
    this.getHomeInfo()
  },
  computed: {
    ...mapState(['city'])
  },
  activated () {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city
      this.getHomeInfo()
    }
  },
  methods: {
    getHomeInfo () {
      Axios.get('./static/mock/index.json?city=' + this.city)
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      let data = res.data
      if (data.ret || data.data) {
        data = data.data
        // console.log(data)
        this.swiperList = data.swiperList
        this.iconList = data.iconList
        this.recommendList = data.recommendList
        this.weekendList = data.weekendList
      }
    }
  }
}
</script>

<style lang="stylus" scoped>

</style>
