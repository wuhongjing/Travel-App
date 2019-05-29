<template>
  <div class="list">
    <div class="item" v-for="(item,index) in ListArr" :key="index">
      <p class="itemTitle">
        <i class="titIcon"></i>{{item.title}}
      </p>
      <p v-if="item.children" class="itemSon">
        <List :ListArr="item.children"></List>
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'List',
  props: {
    ListArr: Array
  }
}
</script>

<style lang="stylus" scoped>
.itemTitle
  line-height: .8rem
  font-size: .32rem
  padding: 0 .2rem
  .titIcon
    display: inline-block
    position: relative
    top: .06rem
    left: .08rem
    width: .36rem
    height: .36rem
    background: url('http://s.qunarzz.com/piao/image/touch/sight/detail.png') 0 -.45rem no-repeat
    margin-right: .1rem
    background-size: .4rem 3rem
.itemSon
  padding: 0 .2rem
</style>
