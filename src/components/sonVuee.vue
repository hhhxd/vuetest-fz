<template>
   <div>
       <div class="v">
        <h1>{{msg}}</h1>
        <button @click="sendMsg">给父组件发消息</button>
       </div>
   </div>
</template>
<script>
   export default {
       data() {
           return {
           }
       },
       props:['msg'],
       methods:{
           sendMsg(){
            //    console.log(this);
               this.$parent.$emit('receiveMsg','今年7岁!')  //发射事件
           }
       }
   }
</script>
<style scoped>
.v{
    height:200px;
    width:100%;
    background-color:yellowgreen;
}
</style>
