<template>
  <section class="alphabet">
    <ul class="itemWrap">
      <li class="item" v-for="(item,key) in cities" :key="key">{{key}}</li>
    </ul>
  </section>
</template>

<script>
export default {
  name: 'Alphabet',
  props: {
    cities: Object
  }
}
</script>

<style lang="stylus" scoped>
@import '~style/varibles.styl'

.itemWrap
   position: absolute
   top: 1.58rem
   right: 0
   bottom: 0
   display: flex
   flex-direction: column
   justify-content: center
   width: .5rem
   font-size: .25rem
   line-height: 0.36rem
   text-align: center
   color: $bgcolor
</style>
