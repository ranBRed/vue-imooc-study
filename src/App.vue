<template>
  <div id="app">
<!--      与Detail进行匹配的组件都不会缓存下来-->
    <keep-alive exclude="Home">
      <router-view/>
    </keep-alive>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>
</style>
