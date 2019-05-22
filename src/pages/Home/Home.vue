<template>
  <section class="home">
    <Header :city="city"></Header>
    <indexSwiper :swiperList="swiperList"></indexSwiper>
    <Nav :iconList="iconList"></Nav>
    <Recommend :recommendList="recommendList"></Recommend>
    <Weekend :weekendList="weekendList"></Weekend>
  </section>
</template>

<script>
import Header from './components/Header'
import indexSwiper from './components/Swiper'
import Nav from './components/Nav'
import Recommend from './components/Recommend'
import Weekend from './components/Weekend'
import Axios from 'axios'

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
      city: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  mounted () {
    this.getHomeInfo()
  },
  methods: {
    getHomeInfo () {
      Axios.get('./static/mock/index.json')
        .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      let data = res.data
      if (data.ret || data.data) {
        data = data.data
        // console.log(data)
        this.city = data.city
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
