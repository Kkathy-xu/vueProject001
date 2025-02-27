<template>
    <h3>传递数据</h3>
    <h3>{{ message }}</h3>
    <ul>
        <li v-for="(item,index) in names" key="index">{{ item }}</li>
    </ul>
    <button @click="clickThrough">点击</button>
</template>

<script>
export default{
    name:"myCom",
    // props:{
    //     message:{
    //         type:String,
    //         default:""
    //     },
    //     names:{
    //         type:Array,
    //         default:function(){
    //             return []
    //         }
    //     }
    // },
    methods:{
        clickThrough(){
            this.$emit("onEvent",this.message)
        }
    },
    data(){
        return{
            message:"我是component数据"
        }
    },
}

</script>

<style scoped>
h3{
    color:red;
    font-size: 40px;
    background-color: antiquewhite;
}
</style>