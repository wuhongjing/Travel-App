<template>
  <section class="city">
    <CityHeader></CityHeader>
    <CitySearch></CitySearch>
  </section>
</template>

<script>
import CityHeader from './components/CityHeader'
import CitySearch from './components/CitySearch'

export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<style scoped>

</style>
