<script setup lang="ts">

</script>

<template>
  <div>
    <h1>APP</h1>
    声明式路由跳转 两种方式 加入 replace 不会留下历史记录
    <router-link replace to="/login"><button>login</button></router-link>
    配置路由的 index 里面添加 name
    <router-link :to="{ name: 'home' }" style="margin-left: 10px"><button>home</button></router-link>
    <router-view></router-view>
  </div>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}

.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
