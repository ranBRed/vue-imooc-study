<template>
  <div class="container" @click="handleGallaryClick">
    <div class="wrapper">
      <swiper :options="swiperOption">
        <swiper-slide
          v-for="(item,index) of imgs"
          :key="index"
        >
          <img :src="item" alt="/" class="gallary-img"/>
        </swiper-slide>
        <div class="swiper-pagination" slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
    import {swiperSlide,swiper} from 'vue-awesome-swiper'
    export default {
        name: "Gallary",
        props: {
          imgs: {
            type: Array,
            default () {
              return []
            }
          }
        },
        components: {
          swiper,
          swiperSlide
        },
        data () {
          return {
            swiperOption: {
              pagination: '.swiper-pagination',
              paginationType: 'fraction',
              observeParents: true,
              observer: true
            }
          }
        },
        methods: {
          handleGallaryClick () {
            this.$emit('close')
          }
        }
    }
</script>

<style lang="stylus" scoped>
  .container >>> .swiper-container
    overflow: inherit
  .container
    display: flex
    flex-direction: column
    justify-content: center
    z-index: 99
    position: fixed
    left: 0
    right: 0
    top: 0
    bottom: 0
    background: #000
    .wrapper
      height: 0
      width: 100%
      padding-bottom: 100%
      .gallary-img
        width: 100%
      .swiper-pagination
        color: #ffffff
        bottom: -1rem
</style>
