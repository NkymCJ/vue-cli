<template>
  <div class="header">
    <h2>待办事项</h2>
    <div class="nav">
      <router-link to="/">主页</router-link>
      <router-link to="/about">关于</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Header'
}
</script>

<style lang="scss" scoped>
  .header {
    background: #333;
    color: #fff;
    text-align: center;
    padding: 10px;
    .nav {
      a {
        color: #fff;
        padding-right: 5px;
        text-decoration: none;
      }
    }
  }
</style>
