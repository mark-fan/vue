<script>
export default{
  data:function(){
   return {
    message:"你好",
    id:1,
    user:{
      name:"mark",
      age:16,
      sex:"男"
    }
   }
  },
  methods:{
    
  },
  // watch:{ //监听数据的变化,但是不能监听对象的属性变化
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
  watch:{//不能监听对象的属性变化,需要使用到深度监听
    message:{
    immediate:true,//初始化的时候调用函数
    handler:function(newValue){
      console.log(newValue);
      if(newValue.length<5 ||newValue.length>10){
        console.log("输入框的内容不能小于5或者大于10");
      }
    }
  },
  // user:function(newValue){
  //   console.log(newvalue);
  // }

  // user:{
  //   handler:function(newValue){
  //     console.log(newValue);
  //   },
  //   deep:true, //表示是否深度监听，侦听器会一层层向下遍历
  // }

  "user.name":{ //使用字符串的方式进行优化 实现对象单属性的监听
    handler:function(newValue){
      console.log(newValue);
    },
    deep:true, //表示是否深度监听，侦听器会一层层向下遍历
  }
  }
}
</script>

<template>
  <button @click="message='你好'">改变message</button>
  <!-- 数据的双向绑定 -->
  <input type="text" v-model="message">
  <p>{{user.name}}</p>
  <button @click="user.name='lisi'">修改名字</button>
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
