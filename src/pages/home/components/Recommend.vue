<template>
  <div>
    <div class="title-group">
      <span class="title">热销推荐</span>
      <a class="title-more" href="http://touch.piao.qunar.com/touch/weekHotSales.htm?cityName=三亚">全部榜单</a>
    </div>
    <ul>
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <img class="item-img" :src="item.imgUrl" />
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
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
  .item
    overflow: hidden
    display: flex
    height: 2.2rem
    .item-img
      width: 2rem
      height: 2rem
      padding: .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
      .item-title
        line-height: .8rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-button
        line-height: .6rem
        margin-top: .16rem
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #fff
</style>
