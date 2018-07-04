<template>
   <div>
    <div class="ez">
      <h1>子组件SON</h1>
      <h2>{{msg}}</h2>
      <button @click="getmsg">点击查看父组件传递的常量信息</button>
      
    </div>
   </div>
</template>
<script>
  export default {
    name: 'sonVue',
    data () {
      return {

      } 
    },
    props:['msg'],
    methods:{
      getmsg(){
        alert('信息是:'+this.$props.msg)
      }
    }

  }
</script>
<style scoped>
.ez{
  height:300px;
  width:100%;
  background-color:pink;
}
</style>
