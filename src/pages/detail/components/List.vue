<template>
  <div>
    <div
      class="item"
      v-for="(item,index) of list"
      :key="index"
      @click="handleShowClick(index)"
    >
      <list-item
        :item="item"
      ></list-item>
<!--      <div class="item-title border-bottom">-->
<!--        <span class="item-title-icon"></span>-->
<!--        {{item.title}}-->
<!--        <button class="item-button" >展示</button>-->
<!--      </div>-->
<!--      <div v-if="handleShow(index)" class="item-children">-->
<!--&lt;!&ndash;        <detail-list :list="item.children"></detail-list>&ndash;&gt;-->
<!--        <div>展示</div>-->
<!--      </div>-->
    </div>
  </div>
</template>

<script>
    import ListItem from './ListItem'
    export default {
        name: "DetailList",
      components: {ListItem},
      props: {
          list: Array,
          len: Array
        },
        data () {
          return {
            showChildren: this.len,
            myList: this.list
          }
        },
        methods: {
          handleShowClick(index) {
          },
          handleShow(index) {
            return Boolean(this.showChildren[index])
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
