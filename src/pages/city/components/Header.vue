<template>
  <div class="header">
    城市选择
    <router-link to="/">
      <div class="iconfont header-icon">&#xe646;</div>
    </router-link>
  </div>
</template>

<script>
    export default {
        name: "Header"
    }
</script>

<style lang="stylus" scoped>
  @import "~styles/varibles.styl"
  .header
    position: relative
    overflow: hidden
    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    color: #ffffff
    background: $backgroundColor
    font-size: .32rem
    .header-icon
      position: absolute
      top: 0
      left: 0
      width: .64rem
      text-align: center
      font-size: .4rem
      color: #ffffff
</style>
