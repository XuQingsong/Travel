<template>
  <div class="alphabet">
    <ul>
      <li class="item" v-for="item of letters" :key="item"
      @click="handleLetterClick(item)">{{item}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object
  },
  computed: {
    letters () {
      const letters = []
      for (let p in this.cities) {
        letters.push(p)
      }
      return letters
    }
  },
  methods: {
    handleLetterClick (letter) {
      this.$emit('change', letter)
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .alphabet
    position: fixed
    display: flex
    flex-direction: column
    top: 2rem
    right: 0
    bottom: 0
    width: .4rem
    .item
      line-height: .4rem
      text-align: center
      color: $bgColor
</style>
