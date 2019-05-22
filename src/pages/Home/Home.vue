<template>
  <section class="home">
    <Header></Header>
    <indexSwiper></indexSwiper>
    <Nav></Nav>
    <Recommend></Recommend>
    <Weekend></Weekend>
  </section>
</template>

<script>
import Header from './components/Header'
import indexSwiper from './components/Swiper'
import Nav from './components/Nav'
import Recommend from './components/Recommend'
import Weekend from './components/Weekend'

export default {
  name: 'Home',
  components: {
    Header,
    indexSwiper,
    Nav,
    Recommend,
    Weekend
  }
}
</script>

<style lang="stylus" scoped>

</style>
