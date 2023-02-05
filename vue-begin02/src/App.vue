<script>
export default{
  data:function(){
   return {
    message:"hello world",
    id:1
   }
  },
  // 计算属性  
  computed:{ //只要依赖值不变  就不会重新计算 计算属性将基于他们的响应依赖关系缓存，提高性能
    reverseMessage:function(){
      console.log("计算属性");
      return this.message.split(' ').reverse().join(' ')
    }
  },
  methods:{
    reverseMsg:function(){
      console.log("methods");
      return this.message.split('').reverse().join('')
    }
  }

}
</script>



<template>
  <p>{{message}}</p>
  <!-- 第一种：使用js表达式 -->
  <p>{{message.split(' ').reverse().join(' ')}}</p>
  <p>{{message.split(' ').reverse().join(' ')}}</p>
  <p>{{message.split(' ').reverse().join(' ')}}</p>
  <!-- 第二种使用计算属性 -->
  <p>{{reverseMessage}}</p>
  <p>{{reverseMessage}}</p>
  <p>{{reverseMessage}}</p>
  <!-- 第三种 使用methods方法 -->
  <p>{{reverseMsg()}}</p>
  <p>{{reverseMsg()}}</p>
  <p>{{reverseMsg()}}</p>
  <button @click="message='nihao'">改变message</button>

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
