<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img :src="bannerImg" alt="/" class="banner-img"/>
      <div class="banner-info">
        <div class="banner-title">
          {{this.signName}}
        </div>
        <div class="banner-number">
          <span class="iconfont bannericon">&#xe635;</span>
          {{this.bannerImgs.length}}
        </div>

      </div>
    </div>
    <fade-animation>
      <gallary
        :imgs="bannerImgs"
        @close="handleGallaryClose"
        v-show="showGallary"
      >
      </gallary>
    </fade-animation>
  </div>
</template>

<script>
    import FadeAnimation from 'common/fade/FadeAnimation'
    import Gallary from 'common/gallary/Gallary'
    export default {
        name: "DetailBanner",
        components: {
          Gallary,
          FadeAnimation
        },
        data() {
          return {
            showGallary: false
          }
        },
        methods:{
          handleBannerClick() {
            this.showGallary = true
          },
          handleGallaryClose() {
            console.log('点击关闭')
            this.showGallary = false
            console.log(this.showGallary)
          }
        },
        props: {
          signName: String,
          bannerImg: String,
          bannerImgs: Array
        }
    }
</script>

<style lang="stylus" scoped>
  .banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
      with: 100%
    .banner-info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: 0
      line-height: .6rem
      color: #ffffff
      background-image: linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
      .banner-title
        flex: 1
        font-size: .32rem
        padding: 0 .2rem
      .banner-number
        height: .32rem
        line-height: .32rem
        margin-top: .14rem
        padding: 0 .4rem
        border-radius: .2rem
        background: rgba(0,0,0,.8)
        font-size: .24rem
        .banner-icon
          font-size: .24rem
</style>
