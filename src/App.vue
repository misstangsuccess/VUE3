<template>
<p>count{{count}}</p>
  <!-- <p>count{{state.count}}</p> -->
  <p>{{num}}</p>
  <button @click="handleClick">按钮</button>
  <p></p>
  <ul>
    <li  v-for="(value, key) in person" :key="key">{{key}}---{{value}}</li>
  </ul>
  <button @click="person.age=18">按钮</button>
  <!-- 在v3中数据不管是定义好的还是后来添加的都是响应式 -->
</template>

<script>
// import { reactive,toRefs,onMounted,onBeforeUnmount,onBeforeUpdate,ref} from "vue";
export default {
  name: 'App',
  data(){
    return{
      person:{
        name:"lily"
      }
    }
  }
  //reactive定义成响应式数据
  //setup定义API接口
  //toRefs()  展开响应式数据,可以单个使用
  //生命周期onMounted,onBeforeUnmount,onBeforeUpdate
  /* setup() {
    console.log("setup",this);//没有this
    //定义单个响应式数据
    const num=ref(1)
    const state = reactive({
      count:0
    })
    const handleClick=()=>{
      state.count++
    }
    onBeforeUpdate(()=>{
      console.log("onBeforeUpdate");
    })
    onMounted(()=>{
      console.log("onMounted");
    })
    onBeforeUnmount(()=>{
      console.log("onBeforeUnmount");
    })
    //返回对象,作为数据添加到this上
    return {
      //state,
      ...toRefs(state),//展开数据
      handleClick,
      num
    }
  } */
}
</script>

<style>
</style>
