<template>
  <section class="city">
    <CityHeader></CityHeader>
  </section>
</template>

<script>
import CityHeader from './components/CityHeader'
export default {
  name: 'City',
  components: {
    CityHeader
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
