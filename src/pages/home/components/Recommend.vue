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
  data () {
    return {
      list: [{
        id: '00001',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1707/c7/c7f3baa7a5094e3ca3.img.jpg_200x200_1e7123ce.jpg',
        title: '三亚海上观光巴士',
        desc: '三亚海上观光巴士好玩好玩'
      }, {
        id: '00002',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1412/e9/d5c72454d47eda983bd4e857c9c361d8.water.jpg_200x200_5870d2ca.jpg',
        title: '分界洲岛',
        desc: '分界洲岛好玩好玩'
      }, {
        id: '00003',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1702/e1/e10c8c5bec0c8e02a3.img.png_200x200_efcaf78c.png',
        title: '亚龙湾热带天堂森林公园',
        desc: '亚龙湾热带天堂森林公园好玩好玩'
      }, {
        id: '00004',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1504/a7/a71c66e94b9d7f2f.water.jpg_200x200_eb3baf53.jpg',
        title: '三亚梦幻水上乐园',
        desc: '三亚梦幻水上乐园好玩好玩'
      }, {
        id: '00005',
        imgUrl: 'http://img1.qunarzz.com/wugc/p189/201206/12/a3ace34bc010041193835fbb.jpg_200x200_84bd8f96.jpg',
        title: '南山文化旅游区',
        desc: '南山文化旅游区好玩好玩'
      }]
    }
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
