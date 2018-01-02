<template>
  <div class="hello">
    {{msgComputed}}
    <input type="text" v-model.lazy="msg"/>
    <ul>
    	<li v-for="(item,index) in list">{{index+":"+item.name+"/"+item.price}}</li>
    	<button @click="addList">数据监听</button>
    </ul>
    <slot name="footer">no slot</slot>
    <slot name="header">no slot</slot>
    
  </div>
  
</template>

<script>
import Vue from 'vue'
export default {
 
  data () {
    return {
      msg: '',
      list:[
      	{"name":"apple",price:24},
      	{"name":"banana",price:21}
      ]
    }
  },
 	computed:{
 		msgComputed(){
 			return this.msg+"这是计算的属性"
 		}
 	},
 	methods:{
 		addList(){
 			Vue.set(this.list,2,{name:"mango",price:88})
 		}
 	},
 	watch:{
 		list(){
 			console.log("watch")
 		}
 	}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.hello{border: 1px solid #ddd;}
</style>
