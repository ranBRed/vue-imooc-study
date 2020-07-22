<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiper">
      <swiper-slide v-for="item of list" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl" :alt="'/' + item.id">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
    import {swiper,swiperSlide} from 'vue-awesome-swiper'
    export default {
        name: "HomeSwiper",
        props: {
          list: Array
        },
        components:{
          swiperSlide,
          swiper
        },
        data () {
          return {
            swiperOption: {
              pagination: '.swiper-pagination',
              // autoplay: 1000,
              autoplay: true,
              speed:1000,
              loop: true
            }
          }
        },
        computed: {
          showSwiper () {
            return this.list.length > 0
          }
        },
        beforeUpdate() {
          console.log('activated')
          console.log(this.$data.swiperOption)
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
    padding-bottom: 31.25%
    background: #eee
    .swiper-img
      width: 100%
</style>
