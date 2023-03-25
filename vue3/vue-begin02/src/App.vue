<script>
export default {
  data: function () {
    return {
      message: "HelloWorld",
      isActive:true,
      error:{},
      classObj:{
        active:true,
        helloWorld:true
      }
    };
  },
  computed:{
    classObjCom:function(){
      return {
        active:this.isActive && !this.error,
        helloWorld:this.error
      }
    }
  }
}
</script>

<template>
<div>
  <!-- 第一种，放置字符串 -->
  <p class="active">hello</p>
  <!-- 第二种，放置对象 -->
  <!-- <p :class="{类名:boolean值}">hello1</p> -->
  <p :class="{active:isActive}">hello1</p>
  <p :class="{active:isActive,helloWorld:isActive}">hello1</p>
  <button @click="isActive=!isActive">改变active</button>
  <p :class="{active:isActive}" class="helloWorld">hello1</p>
  <!-- 假如样式比较多的话  使用对象管理 -->
  <p :class="classObj">hello2</p>
  <!-- 放置使用computed -->
  <p :class="classObjCom">helloComputed</p>
</div>
</template>

<style>
.active{
  font-size: 50px;
  color: blue;
}

.helloWorld{
  background-color: pink;
}
</style>
