<template>
  <section class="city">
    <CityHeader></CityHeader>
    <CitySearch :cities="cities"></CitySearch>
    <CityList :cities="cities" :hotCities="hotCities" :letter="letter"></CityList>
    <Alphabet :cities="cities" @change="handlePassMsg"></Alphabet>
  </section>
</template>

<script>
import CityHeader from './components/CityHeader'
import CitySearch from './components/CitySearch'
import CityList from './components/CityList'
import Alphabet from './components/Alphabet'
import Axios from 'axios'

export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    Alphabet
  },
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  methods: {
    getCityInfo () {
      Axios.get('./static/mock/city.json')
        .then(this.getCityInfoSucc)
    },
    getCityInfoSucc (res) {
      console.log(res)
      let data = res.data
      if (data.ret || data.data) {
        data = data.data
        this.cities = data.cities
        this.hotCities = data.hotCities
      }
    },
    handlePassMsg (val) {
      // console.log(val)
      this.letter = val
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>

<style scoped>

</style>
