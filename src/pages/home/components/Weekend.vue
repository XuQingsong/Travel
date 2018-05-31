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
  data () {
    return {
      list: [{
        id: '00001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/5e/6e13db8af6ec30.jpg_r_640x214_5c1b0fa9.jpg',
        title: '三亚必游TOP10',
        desc: '玩转海岛热带雨林，感受独特黎苗文化'
      }, {
        id: '00002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/a4/df8543b6b8506d.jpg_r_640x214_660e1e3a.jpg',
        title: '就是要看海',
        desc: '海上摩托，拖曳伞什么的爽歪歪了'
      }, {
        id: '00003',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/3d/f99f5c73b52c4d.jpg_r_640x214_4e60b24c.jpg',
        title: '寻找最佳潜水地',
        desc: '潜入梦幻海底，看鱼儿穿梭'
      }, {
        id: '00004',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1602/bf/a2ac57b8bfe7cd.jpg_r_640x214_406d4c7e.jpg',
        title: '城会玩儿游艇大趴',
        desc: '酷炫游艇派对，私人订制心跳回忆'
      }, {
        id: '00005',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/3e/a588a413145dbe.jpg_r_640x214_b3729b6e.jpg',
        title: '小清新帆船出海',
        desc: '帆船出海体验，不一样的海上休闲'
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
