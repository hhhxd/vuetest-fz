<template>
   <div class="g">
       <h1>我是全局组件</h1>
       <input type="text" v-model="text">
       翻转后：{{text | conventStr}}
   </div>
</template>
<script>
   export default {
       data() {
           return {
               text:'hello1234'
           }
       },
       //过滤器
       filters: {
           conventStr(str){
               return (str+'').split('').reverse().join('');
           }
       }
   }
</script>
<style scoped>
.g {
    width: 100%;
    height: 200px;
}
</style>
