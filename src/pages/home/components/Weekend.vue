<template>
  <div>
    <div class="title-group">
      <span class="title">周末去哪儿</span>
      <a class="title-more" href="http://touch.piao.qunar.com/touch/weekHotSales.htm?cityName=三亚">查看所有</a>
    </div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <div class="item-img-wrapper">
          <img class="item-img" :src="item.imgUrl" />
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .title-group
    margin-top: .2rem
    background: #eee
    line-height: 1rem
    .title
      padding-left: .2rem
    .title-more
      float: right
      padding-right: .4rem
      font-size: .14rem
  .item-img-wrapper
    height: 0
    padding-bottom: 37.2%
    .item-img
      width: 100%
  .item-info
    overflow: hidden
    padding: .14rem .2rem .2rem .2rem;
    min-width: 0
    .item-title
      line-height: .48rem
      font-size: .28rem
      color: #212121
      ellipsis()
    .item-desc
      line-height: .42rem
      font-size: .24rem
      color: #616161
      ellipsis()
</style>
