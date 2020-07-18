<template>
  <div id="app">
    <keep-alive exclude="Detail">
<!--      与Detail进行匹配的组件都不会缓存下来-->
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
