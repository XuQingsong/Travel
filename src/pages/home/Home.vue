<template>
  <div>
    <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :list="iconList"></home-icons>
    <home-recommend :list="recommendList"></home-recommend>
    <home-weekend :list="weekendList"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
export default {
  name: 'Home',
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      lastCity: '',
      swiperList: [],
      iconList: [],
      recommendList: [],
      weekendList: []
    }
  },
  methods: {

  },
  mounted () {
    const _this = this
    axios.get('/api/index.json')
      .then(function (response) {
        response = response.data
        if (response.ret && response.data) {
          _this.swiperList = response.data.swiperList
          _this.iconList = response.data.iconList
          _this.recommendList = response.data.recommendList
          _this.weekendList = response.data.weekendList
        }
      })
  }
}
</script>

<style></style>
