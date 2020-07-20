<template>
  <div>
    <div class="title">热销推荐</div>
    <ul>
      <li class="item">
        <img class="item-img" src="http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg" alt="/"/>
        <div class="item-info">
          <p class="item-title">东方宫殿建筑代表，世界宫殿建筑典范</p>
          <p class="item-desc">故宫</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
      <li class="item">
        <img class="item-img" src="http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_140x140_80f63803.jpg" alt="/"/>
        <div class="item-info">
          <p class="item-title">东方宫殿建筑代表，世界宫殿建筑典范</p>
          <p class="item-desc">故宫</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
    export default {
        name: "HomeRecommend"
    }
</script>

<style lang="stylus" scoped>
  @import "~styles/mixins.styl"
  .title
    margin-top: .2rem
    line-height: .8rem
    background: #eeeeee
    text-align: center
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    margin-top: .2rem
    background-color: #fcfcfc
    .item-img
      width: 1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
      .item-title
        line-height: .54rem
        font-size: .32rem
        ellipsis()
      .item-desc
        line-height: .4rem
        color: #ccc
        ellipsis()
      .item-button
        line-height: .44rem
        margin-top: .16rem
        background: #ff9300
        padding: 0 .2rem
        border-radius: .06rem
        color: #ffffff
</style>
