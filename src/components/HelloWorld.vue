<template>
  <div class="hello">
    <h3>hi</h3>
    <p>{{ message }}</p>
    <p v-if="flag">true</p>
    <p v-else>false</p>
  </div>
  <button v-on:click="counter+=1">{{counter}}</button>
  <button @click="clickButton2">{{ message }}</button>


  <!-- 实现 ：获取列表人员姓名，并且为每一个人员姓名添加点击时间，点击后显示人员姓名到控制台-->
   <ul>
    <li @click="clickButton(item)" v-for="(item,index) in items" :key="index"> {{ item }} </li>
   </ul>
   <input type="text" v-model.lazy.trim="username">
   <p>{{ username }}</p>

   <!-- <MyCom :message="message" :names="items"/> -->
   <MyCom @onEvent="clickThrough"/>
   
</template>

<script>
import MyCom from './myCom.vue';

//实现：获取列表人员姓名，并且为每一个人员姓名添加点击时间，点击后显示人员姓名到控制台
export default {
  name: 'HelloWorld',
  data(){
    return {
      message:'ceshi',
      flag:true,
      counter:0,
      items:["iwen","ime","kathy"],
      username:""
    }
  },
  methods:{
    clickButton(item){
      console.log(item);
    },
    clickButton2(event){
      // this.message="点击了"
      event.target.innerHTML='ddd'
    },
    clickThrough(data){
      this.mm=data;
      console.log(data);
    }
      
    
  },
  components:{
    MyCom
  }
}
</script>