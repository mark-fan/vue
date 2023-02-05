<script>
export default{
  data:function(){
   return {
    message:"你好",
    id:1
   }
  },
  methods:{
    
  },
  // watch:{ //监听数据的变化
  //   // 每当message发生变化时 就会调用下面的函数
  //   message:function(newValue,oldValue){// 一个数据会影响多个数据
  //     console.log(newValue);
  //     console.log(oldValue);
  //     //执行异步操作或者比较复杂的逻辑代码
  //     if(newValue.length<5 ||newValue.length>10){
  //       console.log("输入框的内容不能小于5或者大于10");
  //     }
  //   }
  // }
  watch:{
    message:{
    immediate:true,//初始化的时候调用函数
    handler:function(newValue){
      console.log(newValue);
      if(newValue.length<5 ||newValue.length>10){
        console.log("输入框的内容不能小于5或者大于10");
      }
    }
  }
  }
}
</script>

<template>
  <button @click="message='你好'">改变message</button>
  <!-- 数据的双向绑定 -->
  <input type="text" v-model="message">
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
