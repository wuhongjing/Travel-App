<template>
  <section class="home">
    <Header></Header>
    <indexSwiper></indexSwiper>
  </section>
</template>

<script>
import Header from './components/Header'
import indexSwiper from './components/Swiper'

export default {
  name: 'Home',
  components: {
    Header,
    indexSwiper
  }
}
</script>

<style lang="stylus" scoped>

</style>
