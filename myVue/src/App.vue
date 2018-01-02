<template>
  <div id="app">
    <Hello-world  @Emit="Emit" :message="'父向子传参数'"/>
    <div>{{lazy}}</div>
    <input type="text" v-model.lazy="lazy"/>
    <div>{{keyDown}}</div>
    <input type="text" v-model="val" @keydown.enter="KeyDown"/>
    <div :is="Computed">
    		<p slot="footer">footer这是插槽</p>
    		<p slot="header">header这是插槽</p>
    </div>
    <directive></directive>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import Computed from "./components/computed.vue"
import directive from "./components/directives.vue"
export default {
  name: 'app',
  data(){
  	return {
  		lazy:"lazy输入",
  		keyDown:"keyDown输入",
  		val:"",
  		Computed
  	}
  },
  components: {
    HelloWorld,
    Computed,
    directive
  },
  methods:{
  	Emit(data){
  		alert("接收到了子组建的参数"+data)
  	},
  	KeyDown(){
  		this.keyDown=this.val
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
