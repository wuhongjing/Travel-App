<template>
  <section class="home">
    <Header></Header>
    <indexSwiper></indexSwiper>
    <Nav></Nav>
    <Recommend></Recommend>
  </section>
</template>

<script>
import Header from './components/Header'
import indexSwiper from './components/Swiper'
import Nav from './components/Nav'
import Recommend from './components/Recommend'

export default {
  name: 'Home',
  components: {
    Header,
    indexSwiper,
    Nav,
    Recommend
  }
}
</script>

<style lang="stylus" scoped>

</style>
