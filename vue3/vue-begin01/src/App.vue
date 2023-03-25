<script>
// 声明式渲染 可以提高开发效率
// App.vue 根组件
export default{
  data:function(){
    return{
      num:1,
      name:"luofan",
      msg:'<h2>标题</h2>',
      id:'d1',
      url:'https://img12.360buyimg.com/seckillcms/s140x140_jfs/t1/51326/23/21454/20614/63d8e210Ff06e6e55/5d859c31a6af098d.jpg.webp',
      antributeName:'id',
      mouseEvent:"click"
    }
  },
  methods:{
    changeName:function(){
      // this指向vue实例
      this.name = 'luofanfan'
    },
    changeColor:function(){
      this.id='d2'
    }
  }
}
</script>

<template>
  <!-- 组件实例的所有property,不管怎么定义 都可以在组件的模板中访问 -->
  <div>
    <p>{{num}}</p>
    <p>{{name}}</p>
    <!-- v-once：当我的数据发生变化，插值处数据不再变化 -->
    <p v-once>{{name}}</p> 
    <button @click="changeName">改变名字</button>
    <p>{{msg}}</p>
    <!-- v-html:将我们的数据当作html显示 -->
    <p v-html="msg"></p>
    <!-- v-bind :基于绑定属性的内容 -->
    <p v-bind:id="id">v-bind绑定</p>
    <img v-bind:src="url">
    <p id="d2">蓝色</p>
    <!-- javaScript表达式 结果是一样的 -->
    <button @click="changeColor">修改颜色</button>
    <button @click="id=d2">修改颜色</button>

    <p>{{num+10}}</p>
    <p>{{name.split('').reverse().join('') }}</p>
    <p v-bind:id="id+1">v-bind绑定</p>
    <!-- v-bind 语法糖 ： -->
    <p :id="id">语法糖</p>
    <!-- v-on :用于监听DOM事件 -->
    <button v-on:click="changeColor">改变颜色</button>
    <!-- v-on 语法糖 @ -->
    <button @click="id=d2">修改颜色</button>
    <!-- 动态参数 -->
    <!-- 动态属性 -->
    <p v-bind:[antributeName]="id">v-bind绑定</p>
    <button @click="antributeName='class'">改变属性</button>
    <!-- 动态事件 -->
    <button @[mouseEvent]="antributeName='class'">改变属性</button>
    <button @click="mouseEvent='mouseover'">改变事件</button>
  </div>
</template>

<style>
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

#d1{
  color: red;
}

#d2{
  color: blue;
}

.d1{
  font-size:50px;
}
</style>
