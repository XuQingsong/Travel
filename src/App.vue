<!-- 以vue结尾的文件都是单文件组件，template是组件的模板，script是组件的 -->
<template>
  <div id="app">
    <keep-alive exclude="Detail">
      <router-view/>
    </keep-alive>
  </div>
</template>

<script>
export default {
  name: 'Home'
}
</script>

<style>

</style>
