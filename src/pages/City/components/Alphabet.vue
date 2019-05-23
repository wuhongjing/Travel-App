<template>
  <section class="alphabet">
    <ul class="itemWrap">
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
      <li class="item">A</li>
    </ul>
  </section>
</template>

<script>
export default {
  name: 'Alphabet'
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
   width: .4rem
   line-height: 0.4rem
   text-align: center
   color: $bgcolor
</style>
