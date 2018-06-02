<template>
  <div class="header">
    城市选择
    <router-link to='/'>
      <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .header
    position: relative
    height: .86rem
    line-height: .86rem
    text-align: center
    background: $bgColor
    color: #fff
    font-size: .32rem
    ellipsis()
    .back-icon
      position: absolute
      top: 0
      left: 0
      color: #fff
      width: .64rem
      font-size: .4rem
      text-align: center
</style>
