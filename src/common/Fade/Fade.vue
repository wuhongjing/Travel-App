<template>
   <transition>
       <slot></slot>
   </transition>
</template>

<script>
export default {
  name: 'Fade'
}
</script>

<style lang="stylus" scope>
.v-enter,.v-leave-top
   opacity:0
.v-enter-active,.v-leave-active
   transition: opacity 0.5s
</style>
