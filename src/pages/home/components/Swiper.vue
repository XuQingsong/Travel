<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  data: function () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      list: [{
        id: '00001',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/99/74349dce41d79002.jpg_750x200_e619a2d8.jpg'
      }, {
        id: '00002',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/3e/4d6e12949f74fc02.jpg_750x200_22aba1bb.jpg'
      }]
    }
  }
}
</script>
<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background: #fff
  .wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 26.67%
    background: #eee
    .swiper-img
      width: 100%
</style>
