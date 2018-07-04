<template>
  <div id="app">
    <img src="./assets/logo.png">
    <button @click="receiveMsg">父组件开始接收消息-按钮</button>
    <router-view/>
    <sonVue msg="father to son!"></sonVue>
    <sonVuee v-bind:msg="text"></sonVuee>
    <global></global>
  </div>
</template>

<script>
import sonVue from './components/sonVue';
import sonVuee from './components/sonVuee';
export default {
  name: 'App',
  data(){
    return{
      text:'hello'
    }
  },
  components: {
        sonVue,sonVuee
  },
  methods:{
    receiveMsg(){
      // console.log(this);
      this.$on('receiveMsg',function(msg){
        alert("子组件传来的值是:"+msg)
      })
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
