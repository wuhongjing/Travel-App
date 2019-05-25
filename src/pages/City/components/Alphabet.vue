<template>
  <section class="alphabet">
    <ul class="itemWrap">
      <li class="item"
          v-for="item in letters"
          :key="item"
          :ref="item"
          @click="handleCityClick"
          @touchstart="handleTouchStart"
          @touchmove="handleTouchMove"
          @touchend="handleTouchEnd"
      >
      {{item}}
      </li>
    </ul>
  </section>
</template>

<script>
export default {
  name: 'Alphabet',
  props: {
    cities: Object
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    handleCityClick (e) {
      // console.log(e.target.innerText)
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setInterval(() => {
          const touchY = e.touches[0].clientY - 84
          const index = Math.floor((touchY - this.startY) / 18)
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 10)
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
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
  font-size: .26rem
  line-height: 0.36rem
  text-align: center
  color: $bgcolor
</style>
