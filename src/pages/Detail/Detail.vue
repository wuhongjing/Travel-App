<template>
  <div class="detail">
    <Banner :sightName="sightName" :bannerImg="bannerImg" :gallaryImgs="gallaryImgs"></Banner>
    <Header></Header>
    <List :ListArr="categoryList"></List>
    <div class="content">
    </div>
  </div>
</template>

<script>
import Banner from './components/Banner'
import Header from './components/Header'
import List from './components/List'
import Axios from 'axios'

export default {
  name: 'Detail',
  components: {
    Banner,
    Header,
    List
  },
  data () {
    return {
      sightName: '',
      bannerImg: '',
      gallaryImgs: [],
      categoryList: []
    }
  },
  methods: {
    getDetailInfo () {
      Axios.get('./static/mock/detail.json?id=' + this.$route.params.id)
        .then(this.DetailInfoSucess)
    },
    DetailInfoSucess (res) {
      let data = res.data
      console.log(data)
      if (data.ret && data.data) {
        data = data.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.gallaryImgs = data.gallaryImgs
        this.categoryList = data.categoryList
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
.content
  height: 30rem
</style>
