<template>
  <section class="citySearch">
    <input type="text" class="searchInput" placeholder="输入城市名或拼音" />
  </section>
</template>

<script>
export default {
  name: 'citySearch'
}
</script>

<style lang="stylus" scoped>
@import '~style/varibles.styl'

.citySearch
  height: .72rem
  background: $bgcolor
  padding: 0 .15rem
  .searchInput
    width: 100%
    height:.62rem
    line-height: .62rem
    padding:0 0.1rem
    box-sizing: border-box
    text-align: center
    border-radius: 0.06rem
    color: #666
</style>
