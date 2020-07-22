<template>
  <div>
    <home-header></home-header>
    <home-swiper :list = "swiperList"></home-swiper>
    <home-icon :list = "iconList"></home-icon>
    <home-recommend :list = "recommendList"></home-recommend>
    <home-weekend :list = "weekendList"></home-weekend>
  </div>
</template>

<script>
    import HomeHeader from './components/Header'
    import HomeSwiper from './components/Swiper'
    import HomeIcon from './components/Icon'
    import HomeRecommend from './components/Recommend'
    import HomeWeekend from './components/Weekend'
    import axios from 'axios'
    import {mapState} from 'vuex'
    export default {
        name: "Home",
        components: {
          HomeHeader,
          HomeSwiper,
          HomeIcon,
          HomeRecommend,
          HomeWeekend
        },
        data (){
          return {
            lastCity: '',
            swiperList: [],
            iconList: [],
            recommendList: [],
            weekendList: []
          }


        },
        computed: {
          ...mapState(['city'])
        },
        mounted() {
          console.log('mounted')
          this.lastCity = this.city
          this.getHomeInfo()
        },
        methods: {
          getHomeInfo () {
            let url
            if (Math.random() > 0.5){
              url = '/api/index.json?city='
            } else{
              url = '/api/index-xian.json?city='
            }
            axios.get(url + this.city)
              .then(this.getHomeInfoSucc)
          },
          getHomeInfoSucc (res) {
            res = res.data
            if (res.ret && res.data){
              const data = res.data
              this.swiperList = data.swiperList
              this.recommendList = data.recommendList
              this.weekendList = data.weekendList
              this.iconList = data.iconList
            }
          }
        },
        activated () {
          console.log('activated')
          console.log(this.$data.swiperList)
          if (this.lastCity !== this.city) {
            this.lastCity = this.city
            this.getHomeInfo()
          }
        },
        deactivated() {
          console.log('deactivated')
        }
    }
</script>

<style lang="stylus" scoped>

</style>
