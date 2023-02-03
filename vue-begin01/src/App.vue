<script>
//声明式渲染 可以提高开发效率
export default{
  data(){
    return{
      num:0,
      name:"zhangsan"
    }
  }
}
</script>

<template>
  <div>
    <p>{{num}}</p>
    <p>{{name}}</p>
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
