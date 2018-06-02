<template>
  <div>
    <div class="search" >
      <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音" >
    </div>
    <div class="wrapper" ref="wrapper" v-show="keyword">
      <ul class="content">
        <li class="item border-bottom" v-for="item of list" :key="item.id"
        @click="handleCityClick(item.name)">{{item.name}}</li>
        <li class="search-item border-bottom" v-show="hasNoData">
          没有找到匹配数据
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import Bscroll from 'better-scroll'
import { mapMutations } from 'vuex'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      list: [],
      timer: null
    }
  },
  computed: {
    hasNoData () {
      return !this.list.length
    }
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach((value) => {
            if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  },
  methods: {
    handleCityClick (city) {
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .search
    height: .68rem
    background: $bgColor
    padding: 0 .5rem
    .search-input
      box-sizing: border-box
      height: .5rem
      width: 100%
      padding: 0 .1rem
      border-radius: .08rem
      text-align: center
      color: #333
  .wrapper
    z-index: 1
    overflow: hidden
    position: absolute
    top: 1.54rem
    left: 0
    right: 0
    bottom: 0
    background: #eee
    .item
      line-height: .76rem
      font-size: .28rem
      padding-left: .2rem
</style>
