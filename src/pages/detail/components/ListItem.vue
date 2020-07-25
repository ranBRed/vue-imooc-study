<template>
  <div>
    <div class="item-title border-bottom">
      <span class="item-title-icon"></span>
      {{item.title}}
      <button class="item-button" @click="handleShow">展示</button>
    </div>
    <div v-if="show" class="item-children">
      <!--        <detail-list :list="item.children"></detail-list>-->
      <div>展示</div>
    </div>
  </div>

</template>

<script>
    export default {
        name: "ListItem",
        props:{
          item: Object
        },
        data () {
          return{
            show: false
          }
        },
        methods: {
          handleShow() {
            this.show = !this.show
          }
        }
    }
</script>

<style lang="stylus" scoped>
  .item-title-icon
    position: relative
    left: .06rem
    top: .06rem
    display: inline-block
    width: .36rem
    height: .36rem
    background: url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
    margin-right: .1rem
    background-size: .4rem 3rem
  .item-button
    margin-top: .15rem
    float: right
    font-size: .26rem
    height: .5rem
    width: 1rem
  .item-title
    line-height: .8rem
    font-size: .32rem
    padding: 0 .2rem
  .item-children
    padding: 0 .2rem
</style>
