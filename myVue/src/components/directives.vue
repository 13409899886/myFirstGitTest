<template>
  <div class="hello">
    
    <input type="text" placeholder="自定义指令" v-focus="'val'"/>
    
  </div>
  
</template>

<script>
export default {
 	directives:{
	 	focus:{
	 		inserted(el,bind){
	 			el.focus()
	 			console.log(bind)
	 		}
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
